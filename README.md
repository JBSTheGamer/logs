// ======================================================
// Vein Miner (High-Energy Gold Edition)
// Author: You & ChatGPT
// Description:
// Adds high-energy magnetic item suction and vein mining with
// gold spark trails, configurable UI, and persistent spark toggle.
// ======================================================

// ------------------------------------------------------
// CONFIGURATION SECTION – tweak values here
// ------------------------------------------------------
const VMConfig = {
    // --- Core Magnet Settings ---
    EnableMagnet: true,         // Master switch for magnet system
    DefaultRadius: 40,          // Starting suction radius (in tiles)
    MaxRadius: 200,             // Maximum slider radius (in tiles)
    BaseSpeed: 0.15,            // Min speed for far items
    MaxSpeed: 2.35,             // Max pull speed near player
    StrengthCurve: 1.7,         // Acceleration curve (higher = sharper ramp)

    // --- Spark Trail Visuals ---
    EnableSparks: true,         // Initial default (persisted later)
    SparkStyle: "Gold",         // "Gold", "Electric", "Rainbow"
    SparkDensity: 0.35,         // Chance per tick per item to spawn spark
    SparkScale: 1.2,            // Dust particle scale
    SparkBehavior: "MovingOnly",// "MovingOnly" or "AlwaysInRange"

    // --- Timing & Vein Miner ---
    RemoveInterval: 5,          // Delay between ore removal updates
    RemovePerInterval: 10,      // How many tiles removed per update
    VacuumDuration: 180,        // Duration (ticks) for active magnet zone
    Neighborhood: "Moore"       // "Moore" (8-way) or "Neumann" (4-way)
};

// ------------------------------------------------------
// INTERNAL PATHS & FILE HANDLING (for persistent Sparks)
// ------------------------------------------------------
const SettingsPath = "/storage/emulated/0/Android/data/com.pixelcurves.terlauncher/"
    + "tl_files/packs/875b5f05-be01-4bbe-8ed6-54128b491bee/settings/veinminer_settings.json";

// Native file utilities
const File = new NativeClass("System.IO", "File");
const Directory = new NativeClass("System.IO", "Directory");
const Encoding = new NativeClass("System.Text", "Encoding");

// Helper: safe read of settings file
function loadSettings() {
    try {
        if (File.Exists(SettingsPath)) {
            const text = File.ReadAllText(SettingsPath);
            const parsed = JSON.parse(text);
            if (typeof parsed.EnableSparks === "boolean") {
                VMConfig.EnableSparks = parsed.EnableSparks;
                tl?.log?.(`[VM] Settings loaded (Sparks: ${parsed.EnableSparks ? "ON" : "OFF"})`);
                return;
            }
        }
        // if invalid or missing, repair
        saveSettings(VMConfig.EnableSparks);
        tl?.log?.("[VM] Settings repaired (default ON)");
    } catch (err) {
        try {
            saveSettings(VMConfig.EnableSparks);
            tl?.log?.("[VM] Settings reset after error");
        } catch(e2){ tl?.log?.("[VM] Settings fatal error"); }
    }
}

// Helper: write settings JSON
function saveSettings(val) {
    try {
        const dir = SettingsPath.substring(0, SettingsPath.lastIndexOf("/"));
        if (!Directory.Exists(dir)) Directory.CreateDirectory(dir);
        const json = JSON.stringify({ EnableSparks: !!val });
        File.WriteAllText(SettingsPath, json, Encoding.UTF8);
    } catch (e) {
        tl?.log?.("[VM] Failed to save settings: " + e);
    }
}

// Load at startup
loadSettings();

// ------------------------------------------------------
// TERRARIA CLASS REFERENCES
// ------------------------------------------------------
const Main      = new NativeClass('Terraria', 'Main');
const TileData  = new NativeClass('Terraria', 'TileData');
const WorldGen  = new NativeClass('Terraria', 'WorldGen');
const HitTile   = new NativeClass('Terraria', 'HitTile');
const TileID_Sets = new NativeClass('Terraria.ID', 'TileID').Sets;
const Vector2   = new NativeClass('Microsoft.Xna.Framework', 'Vector2');
const Tile = Main.tile;
const Ore = TileID_Sets.Ore;
const KillTile = WorldGen.KillTile;
const TileDataGetType = TileData['ushort GetType(int tileIndex)'];

// ------------------------------------------------------
// CORE VEIN MINER CLASS DEFINITION
// ------------------------------------------------------
class VeinMiner {
    static WORLD_WIDTH = 0;
    static WORLD_HEIGHT = 0;
    static WORLD_SIZE = 0;
    static OFFSETS = null;
    static REMOVE_QUEUE = [];
    static REMOVE_SET = new Set();
    static REMOVE_UPDATE_COUNTER = 0;
    static VACUUM_ZONES = [];
    static VACUUM_TTL_TICKS = VMConfig.VacuumDuration;
    static VACUUM_PAD_TILES = VMConfig.DefaultRadius;
    static MagnetEnabled = VMConfig.EnableMagnet;
    static IsInitialized = false;

    // --- Setup / Reset world size ---
    static Initialize() {
        VeinMiner.WORLD_WIDTH = Tile._width;
        VeinMiner.WORLD_HEIGHT = Tile._height;
        VeinMiner.WORLD_SIZE = VeinMiner.WORLD_WIDTH * VeinMiner.WORLD_HEIGHT;
        const w = VeinMiner.WORLD_WIDTH;
        const nbs = {
            "Moore": [w, w+1, 1, -w+1, -w, -w-1, -1, w-1],
            "Neumann": [w, -w, 1, -1]
        };
        VeinMiner.OFFSETS = nbs[VMConfig.Neighborhood] ?? nbs["Neumann"];
        VeinMiner.REMOVE_QUEUE = [];
        VeinMiner.REMOVE_SET.clear();
        VeinMiner.REMOVE_UPDATE_COUNTER = 0;
        VeinMiner.VACUUM_ZONES.length = 0;
        VeinMiner.IsInitialized = true;
    }

    // --- Reinit on world change ---
    static EnsureWorldUpToDate() {
        if (!VeinMiner.IsInitialized ||
            Tile._width  !== VeinMiner.WORLD_WIDTH ||
            Tile._height !== VeinMiner.WORLD_HEIGHT) {
            VeinMiner.IsInitialized = false;
            VeinMiner.Initialize();
        }
    }

    // --- Check if a tile type can be vein mined ---
    static IsTileTypeVeinable(t) {
        return (Ore[t]);
    }

    // --- Coordinate helpers ---
    static Index(x,y){return y*VeinMiner.WORLD_WIDTH+x;}
    static XY(i){return [i%VeinMiner.WORLD_WIDTH, Math.floor(i/VeinMiner.WORLD_WIDTH)];}
    static InBoundsIndex(i){return i>=0 && i<VeinMiner.WORLD_SIZE;}

    // --- Perform vein mining search + mark area for vacuum ---
    static Mine(x,y){
        VeinMiner.EnsureWorldUpToDate();
        const seed = VeinMiner.Index(x,y);
        if(!VeinMiner.InBoundsIndex(seed))return;
        const t = TileDataGetType(seed);
        if(!VeinMiner.IsTileTypeVeinable(t))return;
        const MAX = 5000;
        const stack=[seed];
        if(!VeinMiner.REMOVE_SET.has(seed)){VeinMiner.REMOVE_QUEUE.push(seed);VeinMiner.REMOVE_SET.add(seed);}
        let minX=x,maxX=x,minY=y,maxY=y,added=1;
        while(stack.length){
            const cur=stack.pop();
            for(const o of VeinMiner.OFFSETS){
                const next=cur+o;
                if(!VeinMiner.InBoundsIndex(next))continue;
                if(VeinMiner.REMOVE_SET.has(next))continue;
                const tt=TileDataGetType(next);
                if(tt===t){
                    VeinMiner.REMOVE_QUEUE.push(next);
                    VeinMiner.REMOVE_SET.add(next);
                    stack.push(next);
                    const [nx,ny]=VeinMiner.XY(next);
                    if(nx<minX)minX=nx;if(nx>maxX)maxX=nx;if(ny<minY)minY=ny;if(ny>maxY)maxY=ny;
                    added++;if(added>=MAX){stack.length=0;break;}
                }
            }
        }
        const pad=VeinMiner.VACUUM_PAD_TILES|0;
        VeinMiner.VACUUM_ZONES.push({
            minX:Math.max(0,minX-pad),
            maxX:Math.min(VeinMiner.WORLD_WIDTH-1,maxX+pad),
            minY:Math.max(0,minY-pad),
            maxY:Math.min(VeinMiner.WORLD_HEIGHT-1,maxY+pad),
            ttl:VeinMiner.VACUUM_TTL_TICKS|0
        });
    }
}
// ======================================================
// MAIN UPDATE LOOP + MAGNET PHYSICS + SPARK EFFECTS
// ======================================================

Main.UpdateTime.hook((orig, self) => {
    // Run original Terraria update
    if (self) orig(self); else orig();

    if (!VeinMiner.IsInitialized) return;

    // -------------------------------
    // 1. Handle scheduled ore removal
    // -------------------------------
    if (VeinMiner.REMOVE_UPDATE_COUNTER >= VMConfig.RemoveInterval) {
        let n = Math.min(VMConfig.RemovePerInterval | 0, VeinMiner.REMOVE_QUEUE.length);
        while (n-- > 0) {
            const i = VeinMiner.REMOVE_QUEUE.shift();
            if (i === undefined) break;
            const [x, y] = VeinMiner.XY(i);
            KillTile(x, y, false, false, false);
        }
        VeinMiner.REMOVE_UPDATE_COUNTER = 0;
        if (!VeinMiner.REMOVE_QUEUE.length) VeinMiner.REMOVE_SET.clear();
    }
    VeinMiner.REMOVE_UPDATE_COUNTER++;

    // -------------------------------
    // 2. Magnet effect (item pull)
    // -------------------------------
    if (VeinMiner.MagnetEnabled && VeinMiner.VACUUM_ZONES.length) {
        const p = Main.LocalPlayer;
        if (p) {
            // Player center position
            const px = (p.position?.X ?? p.position?.x ?? 0) + (p.width ?? 0) * 0.5;
            const py = (p.position?.Y ?? p.position?.y ?? 0) + (p.height ?? 0) * 0.5;

            // Check if item is in any active vacuum zone
            const inZone = (ix, iy) =>
                VeinMiner.VACUUM_ZONES.some(
                    z => ix >= z.minX && ix <= z.maxX && iy >= z.minY && iy <= z.maxY
                );

            const arr = Main.item;
            const len = arr?.length ?? 0;

            // Loop through items and apply suction
            for (let i = 0; i < len; i++) {
                const it = arr[i];
                if (!it || !it.active) continue;

                const ix = Math.floor((it.position?.X ?? it.position?.x ?? 0) / 16);
                const iy = Math.floor((it.position?.Y ?? it.position?.y ?? 0) / 16);
                if (!inZone(ix, iy)) continue;

                try {
                    const itemPos = it.position;
                    const distX = px - itemPos.X;
                    const distY = py - itemPos.Y;
                    const dist = Math.sqrt(distX * distX + distY * distY) + 0.001;
                    const nx = distX / dist;
                    const ny = distY / dist;
                    const radiusPx = VeinMiner.VACUUM_PAD_TILES * 16;

                    // --- High-Energy Acceleration Curve ---
                    // Items speed up rapidly as they get closer
                    let strength = 1 - Math.min(1, dist / radiusPx);
                    const speed =
                        VMConfig.BaseSpeed +
                        (VMConfig.MaxSpeed - VMConfig.BaseSpeed) *
                            Math.pow(strength, VMConfig.StrengthCurve);

                    const dx = nx * speed * 16;
                    const dy = ny * speed * 16;

                    // Assign velocity safely (different TL builds handle Vector2 differently)
                    let newVel;
                    try { newVel = new Vector2(dx, dy); }
                    catch (e2) { newVel = { X: dx, Y: dy }; }

                    it.velocity = newVel;
                    it.active = true;
                    it.beingGrabbed = true;
                    if (typeof it.noGrabDelay === "number") it.noGrabDelay = 0;
                    if ("playerIndexTheItemIsReservedFor" in it)
                        it.playerIndexTheItemIsReservedFor = Main.myPlayer | 0;

                    // -------------------------------
                    // 3. Spark trail visuals (Gold)
                    // -------------------------------
                    if (VMConfig.EnableSparks && Math.random() < VMConfig.SparkDensity) {
                        // For "MovingOnly" mode, only spawn if the item is moving
                        if (
                            VMConfig.SparkBehavior === "AlwaysInRange" ||
                            (VMConfig.SparkBehavior === "MovingOnly" &&
                                (Math.abs(it.velocity.X) + Math.abs(it.velocity.Y)) > 0.1)
                        ) {
                            try {
                                const Dust = new NativeClass("Terraria", "Dust");
                                const DustID = new NativeClass("Terraria.ID", "DustID");
                                let dustType = DustID.GoldCoin; // Gold spark default
                                if (VMConfig.SparkStyle === "Electric") dustType = DustID.Electric;
                                else if (VMConfig.SparkStyle === "Rainbow") dustType = DustID.RainbowRod;

                                Dust.NewDust(
                                    it.position,
                                    8, 8,
                                    dustType,
                                    0, 0, 150, 0,
                                    VMConfig.SparkScale
                                );
                            } catch (sparkErr) {
                                // Skip spark errors silently
                            }
                        }
                    }
                } catch (e3) {
                    tl?.log?.("[VM] pull fail: " + e3);
                }
            }
        }

        // -------------------------------
        // 4. Vacuum zone lifetime decay
        // -------------------------------
        for (let z = VeinMiner.VACUUM_ZONES.length - 1; z >= 0; z--) {
            const v = VeinMiner.VACUUM_ZONES[z];
            v.ttl--;
            if (v.ttl <= 0) VeinMiner.VACUUM_ZONES.splice(z, 1);
        }
    }
});

// ======================================================
// VEIN MINER TRIGGER (when block mined)
// ======================================================
HitTile.AddDamage.hook((orig, self, id, d, u) => {
    const dmg = orig(self, id, d, u);
    if (dmg >= 100) {
        const held = Main.LocalPlayer?.HeldItem;
        if (held && held.pick > 0) {
            const data = self.HitTileObjectData, base = id * 7;
            const x = data[base + 0] | 0, y = data[base + 1] | 0;
            VeinMiner.Mine(x, y);
        }
    }
    return dmg;
});
// ======================================================
// USER INTERFACE (DrawWorldCursor Hook)
// ======================================================

try {
    const MainUI = Main;

    // Try to load Color class safely for text drawing
    let ColorUI;
    try { ColorUI = new NativeClass("Microsoft.Xna.Framework", "Color"); }
    catch (e) {
        try { ColorUI = new NativeClass("Terraria.Graphics", "Color"); }
        catch (e2) { ColorUI = { White: 0xffffffff }; }
    }

    // -------------------------------
    // UI STATE OBJECT
    // -------------------------------
    const UIState = {
        visible: true,
        x: 80, y: 120, w: 260, h: 170,
        drag: false, dx: 0, dy: 0,
        ttl: 0, pad: 0
    };

    // Initialize slider visuals from config
    const initUI = () => {
        UIState.ttl = Math.min(1, (VeinMiner.VACUUM_TTL_TICKS | 0) / 600);
        UIState.pad = Math.min(1, (VeinMiner.VACUUM_PAD_TILES | 0) / VMConfig.MaxRadius);
    };
    initUI();

    // -------------------------------
    // TEXT DRAWING HELPERS
    // -------------------------------
    function drawTextSafe(sb, t, x, y) {
        try {
            const f = Main.fontMouseText;
            const Vector2UI = new NativeClass("Microsoft.Xna.Framework", "Vector2");
            const DrawString = sb["void DrawString(Microsoft.Xna.Framework.Graphics.SpriteFont,string,Microsoft.Xna.Framework.Vector2,Microsoft.Xna.Framework.Color)"];
            if (DrawString) DrawString.call(sb, f, t, new Vector2UI(x, y), ColorUI.White);
        } catch (e) { /* ignore text draw errors */ }
    }

    // -------------------------------
    // BASIC UI INTERACTION HELPERS
    // -------------------------------
    function mouseIn(x, y, w, h) {
        const mx = MainUI.mouseX | 0, my = MainUI.mouseY | 0;
        return mx >= x && mx <= x + w && my >= y && my <= y + h;
    }
    function click() { return MainUI.mouseLeft && MainUI.mouseLeftRelease; }

    function button(sb, label, x, y) {
        drawTextSafe(sb, `[ ${label} ]`, x, y);
        return mouseIn(x, y, label.length * 8 + 16, 20) && click();
    }

    function slider(sb, label, x, y, w, val, set) {
        drawTextSafe(sb, label, x, y - 16);
        drawTextSafe(sb, "[" + "-".repeat(Math.max(8, (w / 8) | 0)) + "]", x, y);
        const pos = x + 8 + Math.floor((w - 16) * val);
        drawTextSafe(sb, "◉", pos, y);
        if (mouseIn(x, y - 16, w, 32) && MainUI.mouseLeft) {
            const mx = MainUI.mouseX | 0;
            const t = Math.max(0, Math.min(1, (mx - (x + 8)) / (w - 16)));
            set(t);
        }
    }

    // -------------------------------
    // MAIN RENDER FUNCTION
    // -------------------------------
    function renderUI(sb) {
        const p = UIState;

        // Frame
        drawTextSafe(sb, "┌" + "─".repeat((p.w / 8) | 0) + "┐", p.x, p.y);
        drawTextSafe(sb, "└" + "─".repeat((p.w / 8) | 0) + "┘", p.x, p.y + p.h - 16);
        drawTextSafe(sb, "Vein Miner Controls", p.x + 10, p.y + 10);

        // Draggable top bar
        const bar = mouseIn(p.x, p.y, p.w, 24);
        if (bar && MainUI.mouseLeft && !p.drag) {
            p.drag = true;
            p.dx = (MainUI.mouseX | 0) - p.x;
            p.dy = (MainUI.mouseY | 0) - p.y;
        }
        if (!MainUI.mouseLeft) p.drag = false;
        if (p.drag) {
            p.x = (MainUI.mouseX | 0) - p.dx;
            p.y = (MainUI.mouseY | 0) - p.dy;
        }

        // -------------------------------
        // TOGGLES
        // -------------------------------
        if (button(sb, VeinMiner.MagnetEnabled ? "Magnet: ON" : "Magnet: OFF", p.x + 10, p.y + 34))
            VeinMiner.MagnetEnabled = !VeinMiner.MagnetEnabled;

        if (button(sb, VMConfig.EnableSparks ? "Sparks: ON" : "Sparks: OFF", p.x + 140, p.y + 34)) {
            VMConfig.EnableSparks = !VMConfig.EnableSparks;
            saveSettings(VMConfig.EnableSparks); // persist spark toggle
            tl?.log?.(`[VM] Sparks ${VMConfig.EnableSparks ? "enabled" : "disabled"} (saved)`);
        }

        // -------------------------------
        // SLIDERS
        // -------------------------------
        slider(sb, `Magnet Time: ${(VeinMiner.VACUUM_TTL_TICKS / 60).toFixed(1)}s`,
            p.x + 10, p.y + 68, p.w - 20, UIState.ttl, v => {
                UIState.ttl = v;
                VeinMiner.VACUUM_TTL_TICKS = Math.round(v * 600);
            });

        slider(sb, `Magnet Radius: ${VeinMiner.VACUUM_PAD_TILES | 0} tiles`,
            p.x + 10, p.y + 104, p.w - 20, UIState.pad, v => {
                UIState.pad = v;
                VeinMiner.VACUUM_PAD_TILES = Math.round(v * VMConfig.MaxRadius);
            });

        drawTextSafe(sb, "Drag window / toggle controls", p.x + 10, p.y + 138);
    }

    // -------------------------------
    // HOOK INTO TERRARIA DRAW
    // -------------------------------
    const drawHookName = "void DrawWorldCursor(bool magnify)";
    const drawHook = Main[drawHookName];
    if (!drawHook) tl?.log?.("[UI] No Draw hook found; UI unavailable");

    Main[drawHookName].hook((orig, self, mag) => {
        try {
            if (UIState.visible && Main.spriteBatch)
                renderUI(Main.spriteBatch);
        } catch (e) {
            tl?.log?.("[UI] draw error: " + e);
        }
        orig(self, mag);
    });

} catch (e) {
    tl?.log?.("[UI] init failed: " + e);
}
// ======================================================
// FINAL WRAP-UP AND SAFETY CHECKS
// ======================================================

// --- Post-Initialization Log ---
tl?.log?.("[VM] Vein Miner (High-Energy Gold Edition) initialized successfully.");

// --- Optional Debug Helper ---
// You can toggle this to true to enable verbose debugging in TL logs
const DEBUG_VM = false;
function vmDebug(msg) { if (DEBUG_VM) tl?.log?.("[VM-DEBUG] " + msg); }

// --- Safe integrity checks ---
try {
    if (!Main || !Main.UpdateTime || !HitTile) {
        tl?.log?.("[VM] Warning: Required Terraria hooks not found. Mod may not function on this build.");
    }
    if (!Vector2) {
        tl?.log?.("[VM] Warning: Vector2 not accessible; fallback behavior in effect.");
    }
} catch (verifyErr) {
    tl?.log?.("[VM] Verification error: " + verifyErr);
}

// ======================================================
// DEVELOPER NOTES
// ======================================================
/*
🧩 CONFIGURATION RECAP (edit these at the top):
-----------------------------------------------
VMConfig.EnableMagnet        → Master toggle for magnet system
VMConfig.DefaultRadius       → Starting suction radius (in tiles)
VMConfig.MaxRadius           → Max adjustable radius
VMConfig.BaseSpeed / MaxSpeed→ Magnetic pull speed limits
VMConfig.StrengthCurve       → Adjusts acceleration profile
VMConfig.EnableSparks        → Sparks master toggle (persisted)
VMConfig.SparkBehavior       → "MovingOnly" (default) or "AlwaysInRange"
VMConfig.SparkStyle          → "Gold", "Electric", "Rainbow"
VMConfig.SparkScale          → Particle visual size
VMConfig.RemoveInterval      → Delay between ore removals
VMConfig.RemovePerInterval   → Number of tiles mined per interval

📁 SETTINGS FILE:
-----------------------------------------------
Path:
  /storage/emulated/0/Android/data/com.pixelcurves.terlauncher/
  tl_files/packs/875b5f05-be01-4bbe-8ed6-54128b491bee/settings/veinminer_settings.json

Stores:
  { "EnableSparks": true/false }

Auto repairs if missing or corrupted.

🎮 UI CONTROLS:
-----------------------------------------------
- Drag window by top bar
- [ Magnet: ON/OFF ] toggles suction system
- [ Sparks: ON/OFF ] toggles spark visuals (saves instantly)
- “Magnet Time” slider adjusts vacuum lifetime
- “Magnet Radius” slider adjusts pull distance
- Visible in all worlds (independent of world reload)

🧠 TECHNICAL:
-----------------------------------------------
- Hooks: Main.UpdateTime & DrawWorldCursor
- Physics: High-energy acceleration curve
- Effects: Gold spark trails (DustID.GoldCoin)
- Safe fallback for missing TL classes (Color, Vector2, etc.)
- Logging via tl?.log for debugging convenience
*/

// ======================================================
// END OF FILE
// ======================================================
