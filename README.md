(function () {
  var Main;
  try {
    Main = new NativeClass("Terraria", "Main");
  } catch (e) {
    tl.log("[MoAcc-DRAW] no Terraria.Main: " + e);
    return;
  }

  if (!Main || !Main.DrawInterface || !Main.DrawInterface.hook) {
    tl.log("[MoAcc-DRAW] Main.DrawInterface not hookable");
    return;
  }

  // keep original
  var _orig = Main.DrawInterface;

  Main.DrawInterface.hook(function () {
    // 1) call original FIRST so we don't break the UI
    var r;
    try {
      r = _orig.apply(this, arguments);
    } catch (e) {
      tl.log("[MoAcc-DRAW] original DI threw: " + e);
    }

    // 2) now inspect what we got
    try {
      tl.log("[MoAcc-DRAW] DrawInterface args.len=" + arguments.length);
      for (var i = 0; i < arguments.length; i++) {
        var a = arguments[i];
        tl.log("[MoAcc-DRAW]  arg[" + i + "] = " + (typeof a) + " -> " + a);
      }
    } catch (e2) {
      tl.log("[MoAcc-DRAW] inspect fail: " + e2);
    }

    return r;
  });

  tl.log("[MoAcc-DRAW] hooked Terraria.Main.DrawInterface");
})();
