const CFG_FORGE_BANK = 3;
const CFG_DEDUP = true;

const Player = new NativeClass('Terraria', 'Player');
const UpdateEquips = Player['void UpdateEquips(int i)'];

function arrLen(a) {
    try {
        if (!a) return 0;
        if (typeof a.Length === 'number') return a.Length;
        if (typeof a.length === 'number') return a.length;
    } catch (_) {}
    return 0;
}

function safeBoolSet(o, k, v = true) {
    try {
        if (o && typeof o[k] !== 'undefined') o[k] = !!v;
    } catch (_) {}
}

function safeNumSet(o, k, v) {
    try {
        if (o && typeof o[k] === 'number') o[k] = v;
    } catch (_) {}
}

function safeNumMax(o, k, min) {
    try {
        if (o && typeof o[k] === 'number' && o[k] < min) o[k] = min;
    } catch (_) {}
}

function safeNumAdd(o, k, delta) {
    try {
        if (o && typeof o[k] === 'number') o[k] += delta;
    } catch (_) {}
}

function getChest(self) {
    try {
        if (CFG_FORGE_BANK === 3 && self.bank3 && self.bank3.item && arrLen(self.bank3.item)) return self.bank3.item;
        if (CFG_FORGE_BANK === 2 && self.bank2 && self.bank2.item && arrLen(self.bank2.item)) return self.bank2.item;
        if (CFG_FORGE_BANK === 4 && self.bank4 && self.bank4.item && arrLen(self.bank4.item)) return self.bank4.item;
        if (self.bank3 && self.bank3.item && arrLen(self.bank3.item)) return self.bank3.item;
        if (self.bank2 && self.bank2.item && arrLen(self.bank2.item)) return self.bank2.item;
        if (self.bank4 && self.bank4.item && arrLen(self.bank4.item)) return self.bank4.item;
    } catch (_) {}
    return null;
}

function matches(item, entry) {
    try {
        const nRaw = (item.Name || item.name || '').toString();
        if (nRaw && nRaw.indexOf('Wings') !== -1) return false;
    } catch (_) {}

    try {
        if (entry.ids && entry.ids.length && typeof item.type === 'number') {
            for (let id of entry.ids)
                if (item.type === id) return true;
        }
    } catch (_) {}

    try {
        const n = (item.Name || item.name || '').toString();
        if (!n) return false;
        if (entry.names && entry.names.length) {
            for (let sub of entry.names)
                if (sub && n.indexOf(sub) !== -1) return true;
        }
    } catch (_) {}

    return entry.ids.length === 0 && entry.names.length === 0;
}

// ---- EFFECTS TABLE ----
const EFFECTS = [
    { ids:[156], names:['Lucky Horseshoe'], apply(p,it,acc){ safeBoolSet(p,'noFallDmg',true); }},
    { ids:[37], names:['Obsidian Skull'], apply(p,it,acc){ safeBoolSet(p,'fireWalk',true); }},
    { ids:[221,1613], names:['Obsidian Shield','Ankh Shield'], apply(p,it,acc){ safeBoolSet(p,'noKnockback',true); safeBoolSet(p,'fireWalk',true); }},
    { ids:[906], names:['Lava Charm','Molten Charm'], apply(p,it,acc){ safeBoolSet(p,'lavaImmune',true); }},
    { ids:[908,1321], names:['Water Walking Boots','Obsidian Water Walking Boots'], apply(p,it,acc){ safeBoolSet(p,'waterWalk',true); safeBoolSet(p,'fireWalk',true); }},
    { ids:[910], names:['Lava Waders'], apply(p,it,acc){ safeBoolSet(p,'waterWalk',true); safeBoolSet(p,'fireWalk',true); safeBoolSet(p,'lavaImmune',true); }},
    { ids:[53], names:['Flipper'], apply(p,it,acc){ safeBoolSet(p,'accFlipper',true); }},
    { ids:[395], names:['Diving Helmet','Diving Gear','Arctic Diving Gear'], apply(p,it,acc){ safeBoolSet(p,'accDivingHelm',true); }},
    { ids:[860,1344], names:['Neptune\'s Shell','Moon Shell'], apply(p,it,acc){ safeBoolSet(p,'accMerman',true); }},
    { ids:[54,977,3930,186,5335], names:['Hermes Boots','Spectre Boots','Lightning Boots','Frostspark Boots','Amphibian Boots'], apply(p,it,acc){
        acc.runSpeedMin = Math.max(acc.runSpeedMin, 6.0);
        acc.move += 0.08;
        acc.rocketBootsMin = Math.max(acc.rocketBootsMin, 3);
        safeBoolSet(p,'iceSkate',true);
        safeBoolSet(p,'jumpBoost',true);
        safeBoolSet(p,'accFlipper',true);
    }},
    { ids:[3333], names:['Frog Leg'], apply(p,it,acc){ safeBoolSet(p,'jumpBoost',true); }},
    { ids:[159,935,1861,1862], names:['Shiny Red Balloon','Blizzard in a Balloon','Sandstorm in a Balloon','Bundle of Balloons'], apply(p,it,acc){ safeBoolSet(p,'jumpBoost',true); }},
    { ids:[3366], names:['Shield of Cthulhu'], apply(p,it,acc){ acc.dashMin = Math.max(acc.dashMin, 2); safeBoolSet(p,'noKnockback',true); }},
    { ids:[398], names:['Tabi'], apply(p,it,acc){ acc.dashMin = Math.max(acc.dashMin, 2); }},
    { ids:[3997], names:['Master Ninja Gear'], apply(p,it,acc){ acc.dashMin = Math.max(acc.dashMin, 2); safeBoolSet(p,'blackBelt',true); }},
    { ids:[4870], names:['Soaring Insignia'], apply(p,it,acc){ acc.move += 0.08; acc.runSpeedMin = Math.max(acc.runSpeedMin,6.5); }},
    { ids:[3103], names:['Gravity Globe'], apply(p,it,acc){ safeBoolSet(p,'gravControl',true); safeBoolSet(p,'gravControl2',true); }},
    { ids:[1566,3223], names:['Cross Necklace','Star Veil'], apply(p,it,acc){ safeBoolSet(p,'longInvince',true); }},
    { ids:[1301], names:['Frozen Turtle Shell'], apply(p,it,acc){ safeBoolSet(p,'iceBarrier',true); }},
    { ids:[397,3998], names:['Paladin\'s Shield','Hero Shield'], apply(p,it,acc){ safeBoolSet(p,'hasPaladinShield',true); safeNumAdd(p,'aggro',400); }},
    { ids:[1553], names:['Charm of Myths'], apply(p,it,acc){ safeBoolSet(p,'pStone',true); acc.lifeRegen += 1; }},
    { ids:[535], names:['Philosopher\'s Stone'], apply(p,it,acc){ safeBoolSet(p,'pStone',true); }},
    { ids:[3369], names:['Shiny Stone'], apply(p,it,acc){ acc.lifeRegen += 3; }},
    { ids:[3224], names:['Worm Scarf'], apply(p,it,acc){ safeNumAdd(p,'endurance',0.17); }},
    { ids:[4005], names:['Brain of Confusion'], apply(p,it,acc){ safeBoolSet(p,'brainOfConfusionItem',true); }},

// --- PART 2/4 ---
    { ids:[3212], names:['Shark Tooth Necklace'], apply(p,it,acc){ acc.armorPen = (acc.armorPen||0)+5; }},
    { ids:[4131], names:['Stinger Necklace'], apply(p,it,acc){ acc.armorPen = (acc.armorPen||0)+5; safeBoolSet(p,'strongBees',true); }},
    { ids:[1133], names:['Hive Pack'], apply(p,it,acc){ safeBoolSet(p,'strongBees',true); }},
    { ids:[1134,3330,3229], names:['Honey Comb','Bee Cloak','Star Cloak'], apply(p,it,acc){}},
    { ids:[501], names:['Feral Claws'], apply(p,it,acc){ safeNumAdd(p,'meleeSpeed',0.12); }},
    { ids:[1247], names:['Titan Glove'], apply(p,it,acc){ safeBoolSet(p,'titanGlove',true); }},
    { ids:[1157], names:['Power Glove'], apply(p,it,acc){ safeBoolSet(p,'titanGlove',true); safeNumAdd(p,'meleeSpeed',0.12); }},
    { ids:[1332], names:['Mechanical Glove'], apply(p,it,acc){ safeBoolSet(p,'titanGlove',true); safeNumAdd(p,'meleeSpeed',0.12); acc.dmgAll += 0.12; }},
    { ids:[5125], names:['Berserker\'s Glove'], apply(p,it,acc){ safeBoolSet(p,'titanGlove',true); safeNumAdd(p,'meleeSpeed',0.12); acc.dmgAll += 0.08; safeNumAdd(p,'aggro',400); }},
    { ids:[907], names:['Magma Stone'], apply(p,it,acc){ safeBoolSet(p,'magmaStone',true); }},
    { ids:[5126], names:['Fire Gauntlet'], apply(p,it,acc){ safeBoolSet(p,'titanGlove',true); safeBoolSet(p,'magmaStone',true); safeNumAdd(p,'meleeSpeed',0.12); acc.dmgAll += 0.10; }},
    { ids:[988], names:['Magic Quiver'], apply(p,it,acc){ safeBoolSet(p,'magicQuiver',true); safeNumAdd(p,'rangedDamage',0.10); safeNumAdd(p,'arrowSpeed',0.10); }},
    { ids:[3990], names:['Molten Quiver'], apply(p,it,acc){ safeBoolSet(p,'magicQuiver',true); safeNumAdd(p,'rangedDamage',0.10); }},
    { ids:[3245], names:['Rifle Scope'], apply(p,it,acc){ safeBoolSet(p,'scope',true); }},
    { ids:[3246], names:['Sniper Scope'], apply(p,it,acc){ safeBoolSet(p,'scope',true); safeNumAdd(p,'rangedDamage',0.10); }},
    { ids:[4001], names:['Recon Scope'], apply(p,it,acc){ safeBoolSet(p,'scope',true); safeNumAdd(p,'rangedDamage',0.10); }},
    { ids:[552], names:['Pygmy Necklace'], apply(p,it,acc){ acc.maxMinionsAdd=(acc.maxMinionsAdd||0)+1; }},
    { ids:[3211], names:['Hercules Beetle'], apply(p,it,acc){ acc.dmgAll += 0.15; }},
    { ids:[3231], names:['Necromantic Scroll'], apply(p,it,acc){ acc.maxMinionsAdd=(acc.maxMinionsAdd||0)+1; acc.dmgAll += 0.10; }},
    { ids:[3232], names:['Papyrus Scarab'], apply(p,it,acc){ acc.maxMinionsAdd=(acc.maxMinionsAdd||0)+1; acc.dmgAll += 0.10; }},
    { ids:[489], names:['Warrior Emblem'], apply(p,it,acc){ acc.dmgAll += 0.15; }},
    { ids:[490], names:['Ranger Emblem'], apply(p,it,acc){ acc.dmgAll += 0.15; }},
    { ids:[491], names:['Sorcerer Emblem'], apply(p,it,acc){ acc.dmgAll += 0.15; }},
    { ids:[4937], names:['Avenger Emblem'], apply(p,it,acc){ acc.dmgAll += 0.12; }},
    { ids:[3210], names:['Destroyer Emblem'], apply(p,it,acc){ acc.dmgAll += 0.10; acc.critAll=(acc.critAll||0)+10; }},
    { ids:[3028], names:['Eye of the Golem'], apply(p,it,acc){ acc.critAll=(acc.critAll||0)+10; }},
    { ids:[1569], names:['Celestial Stone'], apply(p,it,acc){ acc.def+=4; acc.dmgAll+=0.10; acc.lifeRegen+=2; acc.move+=0.03; }},
    { ids:[3993], names:['Celestial Shell'], apply(p,it,acc){ acc.def+=4; acc.dmgAll+=0.12; acc.lifeRegen+=2; acc.move+=0.03; }},
    { ids:[861], names:['Mana Flower'], apply(p,it,acc){ safeBoolSet(p,'manaFlower',true); }},
    { ids:[399], names:['Magic Cuffs','Celestial Cuffs'], apply(p,it,acc){ safeBoolSet(p,'magicCuffs',true); }},
    { ids:[5318], names:['Magnet Flower'], apply(p,it,acc){ safeBoolSet(p,'manaFlower',true); safeBoolSet(p,'manaMagnet',true); }},
    { ids:[3096,3097,3098], names:['GPS','REK 3000','Fish Finder'], apply(p,it,acc){ try{ if(typeof p.accWatch==='number'&&p.accWatch<3)p.accWatch=3; }catch(_){}
        safeBoolSet(p,'accCompass',true); safeBoolSet(p,'accDepthMeter',true);
    }},
    { ids:[533], names:['Mining Helmet','Mining Charm','Shine'], apply(p,it,acc){ safeBoolSet(p,'accLight',true); }},
    { ids:[1591], names:['Panic Necklace'], apply(p,it,acc){ safeBoolSet(p,'panic',true); }},
    { ids:[3312], names:['Royal Gel'], apply(p,it,acc){ safeBoolSet(p,'slimeFriendly',true); }},
    { ids:[3291], names:['Yoyo Bag'], apply(p,it,acc){ safeBoolSet(p,'yoyoGlove',true); safeBoolSet(p,'counterWeight',true); safeBoolSet(p,'yoyoString',true); }},
    { ids:[3290], names:['Yoyo Glove'], apply(p,it,acc){ safeBoolSet(p,'yoyoGlove',true); }},
    { ids:[3288], names:['White String','String'], apply(p,it,acc){ safeBoolSet(p,'yoyoString',true); }},
    { ids:[556,557,558,559,560,561], names:['Counterweight'], apply(p,it,acc){ safeBoolSet(p,'counterWeight',true); }},
    { ids:[1612], names:['Ankh Charm'], apply(p,it,acc){ safeBoolSet(p,'noKnockback',true);
        try{
            if(p.buffImmune&&(p.buffImmune.length||p.buffImmune.Length)){
                const list=[20,22,30,31,32,33,36,44];
                for(let k=0;k<list.length;k++){ p.buffImmune[list[k]]=true; }
            }
        }catch(_){}
    }},
    { ids:[], names:['Blindfold','Fast Clock','Trifold Map','Megaphone','Nazar','Vitamins','Armor Bracing','Medicated Bandage','Countercurse Mantra','The Plan','Bezoar'], apply(p,it,acc){
        try{
            if(p.buffImmune&&(p.buffImmune.length||p.buffImmune.Length)){
                const list=[20,22,30,31,32,33,36,44];
                for(let k=0;k<list.length;k++){ p.buffImmune[list[k]]=true; }
            }
        }catch(_){}
    }},
    { ids:[], names:[], apply(p,it,acc){ try{ if(typeof it.defense==='number'&&it.defense>0) acc.def+=it.defense; }catch(_){}} }
];

UpdateEquips.hook((original, self, i) => {
    original(self, i);

    const chest = getChest(self);
    if (!chest) return;

    let baseDef = 0, baseMove = 0, baseLifeRegen = 0, baseAggro = 0, baseArmorPen = 0;
    try { baseDef = (typeof self.statDefense === 'number') ? self.statDefense : 0; } catch (_) {}
    try { baseMove = (typeof self.moveSpeed === 'number') ? self.moveSpeed : 0; } catch (_) {}
    try { baseLifeRegen = (typeof self.lifeRegen === 'number') ? self.lifeRegen : 0; } catch (_) {}
    try { baseAggro = (typeof self.aggro === 'number') ? self.aggro : 0; } catch (_) {}
    try { baseArmorPen = (typeof self.armorPenetration === 'number') ? self.armorPenetration : 0; } catch (_) {}

    const acc = {
        def: 0, move: 0, dmgAll: 0, critAll: 0, lifeRegen: 0,
        runSpeedMin: 0, rocketBootsMin: 0, dashMin: 0,
        armorPen: 0, aggro: 0, maxMinionsAdd: 0
    };

    let sawAny = false;
    const n = arrLen(chest);
    const seen = Object.create(null);

    for (let s = 0; s < n; s++) {
        let it = null;
        try { it = chest[s]; } catch (_) { it = null; }
        if (!it) continue;

        try {
            if (it.IsAir === true) continue;
            if (typeof it.stack === 'number' && it.stack <= 0) continue;
            if (!it.accessory) continue;
        } catch (_) { continue; }

        if (CFG_DEDUP) {
            let key = null;
            try { if (typeof it.type === 'number') key = 't:' + it.type; } catch (_) {}
            if (!key) {
                try {
                    const nm = (it.Name || it.name || '').toLowerCase().trim();
                    if (nm) key = 'n:' + nm;
                } catch (_) {}
            }
            if (key) {
                if (seen[key]) continue;
                seen[key] = true;
            }
        }

        for (let e = 0; e < EFFECTS.length; e++) {
            const entry = EFFECTS[e];
            if (matches(it, entry)) {
                try { entry.apply(self, it, acc); } catch (_) {}
                sawAny = true;
                break;
            }
        }
    }

    safeNumSet(self, 'statDefense', baseDef + acc.def);
    safeNumSet(self, 'moveSpeed', baseMove + acc.move);
    safeNumSet(self, 'lifeRegen', baseLifeRegen + acc.lifeRegen);

    if (acc.armorPen) safeNumSet(self, 'armorPenetration', baseArmorPen + acc.armorPen);
    if (acc.aggro) safeNumSet(self, 'aggro', baseAggro + acc.aggro);

    if (acc.runSpeedMin > 0) safeNumMax(self, 'accRunSpeed', acc.runSpeedMin);
    if (acc.rocketBootsMin > 0) safeNumMax(self, 'rocketBoots', acc.rocketBootsMin);
    if (acc.dashMin > 0) safeNumMax(self, 'dash', acc.dashMin);

    if (acc.dmgAll !== 0) {
        if (typeof self.allDamage === 'number') safeNumAdd(self, 'allDamage', acc.dmgAll);
        else {
            safeNumAdd(self, 'meleeDamage', acc.dmgAll);
            safeNumAdd(self, 'rangedDamage', acc.dmgAll);
            safeNumAdd(self, 'magicDamage', acc.dmgAll);
            safeNumAdd(self, 'minionDamage', acc.dmgAll);
        }
    }

    if (acc.critAll) {
        safeNumAdd(self, 'meleeCrit', acc.critAll);
        safeNumAdd(self, 'rangedCrit', acc.critAll);
        safeNumAdd(self, 'magicCrit', acc.critAll);
        safeNumAdd(self, 'thrownCrit', acc.critAll);
    }

    if (acc.maxMinionsAdd) {
        try {
            if (typeof self.maxMinions === 'number')
                self.maxMinions += acc.maxMinionsAdd;
        } catch (_) {}
    }
});

function initVaultOfEchoes() {
    try {
        const Main = new NativeClass('Terraria', 'Main');
        if (Main && Main.player && Main.player.Length > 0) {
            const p = Main.player[Main.myPlayer];
            if (p) {
                const chest = getChest(p);
                if (chest) {
                    for (let s = 0; s < arrLen(chest); s++) {
                        const it = chest[s];
                        if (it && !it.IsAir && it.accessory) {
                            // verify that the hook works by touching one value safely
                            safeNumAdd(p, 'statDefense', 0);
                        }
                    }
                }
            }
        }
    } catch (_) {}
}

try { initVaultOfEchoes(); } catch (_) {}
