---- Minecraft Crash Report ----
// You should try our sister game, Minceraft!

Time: 2025-12-09 05:40:16
Description: Unexpected error

java.lang.IllegalArgumentException: No model for layer twilightforest:knightmetal_shield#main
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.model.geom.EntityModelSet.bakeLayer(EntityModelSet.java:17) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,re:classloading,pl:accesstransformer:B,pl:mixin:A}
	at TRANSFORMER/twilightforest@4.7.3196/twilightforest.client.ISTER.<init>(ISTER.java:102) ~[twilightforest-1.21.1-4.7.3196-universal.jar%23771!/:4.7.3196] {re:classloading}
	at MC-BOOTSTRAP/com.google.common@32.1.2-jre/com.google.common.base.Suppliers$NonSerializableMemoizingSupplier.get(Suppliers.java:181) ~[guava-32.1.2-jre.jar%23135!/:?] {}
	at TRANSFORMER/twilightforest@4.7.3196/twilightforest.client.event.ClientEvents.handleGameBootup(ClientEvents.java:119) ~[twilightforest-1.21.1-4.7.3196-universal.jar%23771!/:4.7.3196] {re:classloading}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.ConsumerEventHandler.invoke(ConsumerEventHandler.java:27) ~[bus-8.0.5.jar%23110!/:?] {}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.EventBus.post(EventBus.java:360) ~[bus-8.0.5.jar%23110!/:?] {}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.EventBus.post(EventBus.java:328) ~[bus-8.0.5.jar%23110!/:?] {}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.rebuildWidgets(Screen.java:337) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.repositionElements(Screen.java:440) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.resize(Screen.java:446) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.resizeDisplay(Minecraft.java:1326) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/com.mojang.blaze3d.platform.Window.onFramebufferResize(Window.java:251) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:mixins.sodiumextras.json:impl.borderless.BorderlessWindowMixin from mod sodiumextras,pl:mixin:APP:mixins.sodiumextras.json:impl.borderless.accessors.MainWindowAccessor from mod sodiumextras,pl:mixin:APP:sodium-common.mixins.json:core.WindowMixin from mod sodium,pl:mixin:APP:sodium-common.mixins.json:workarounds.context_creation.WindowMixin from mod sodium,pl:mixin:APP:immediatelyfast-common.mixins.json:core.MixinWindow from mod immediatelyfast,pl:mixin:APP:relics.mixins.json:WindowMixin from mod relics,pl:mixin:APP:chloride.mixin.json:BorderlessMixin$WindowMixin from mod chloride,pl:mixin:A,pl:runtimedistcleaner:A}
	at MC-BOOTSTRAP/org.lwjgl.glfw@3.3.3+5/org.lwjgl.glfw.GLFWFramebufferSizeCallbackI.callback(GLFWFramebufferSizeCallbackI.java:44) ~[lwjgl-glfw-3.3.3.jar%23173!/:build 5] {}
	at MC-BOOTSTRAP/org.lwjgl@3.3.3+5/org.lwjgl.system.JNI.invokeV(Native Method) ~[lwjgl-3.3.3.jar%23185!/:build 5] {}
	at MC-BOOTSTRAP/org.lwjgl.glfw@3.3.3+5/org.lwjgl.glfw.GLFW.glfwWaitEventsTimeout(GLFW.java:3509) ~[lwjgl-glfw-3.3.3.jar%23173!/:build 5] {re:mixin}
	at TRANSFORMER/minecraft@1.21.1/com.mojang.blaze3d.systems.RenderSystem.limitDisplayFPS(RenderSystem.java:162) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:sodium-common.mixins.json:workarounds.event_loop.RenderSystemMixin from mod sodium,pl:mixin:APP:flywheel.backend.mixins.json:RenderSystemMixin from mod flywheel,pl:mixin:APP:ponder-common.mixins.json:client.accessor.RenderSystemAccessor from mod ponder,pl:mixin:APP:immediatelyfast-common.mixins.json:hud_batching.compat.MixinRenderSystem from mod immediatelyfast,pl:mixin:APP:owo.mixins.json:ui.RenderSystemMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.runTick(Minecraft.java:1220) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.run(Minecraft.java:807) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.main.Main.main(Main.java:230) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:runtimedistcleaner:A,re:classloading,pl:mixin:APP:cryonicconfig.mixins.json:client.MainMixin from mod cryonicconfig,pl:mixin:A,pl:runtimedistcleaner:A}
	at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:103) ~[?:?] {}
	at java.base/java.lang.reflect.Method.invoke(Method.java:580) ~[?:?] {re:mixin}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.runTarget(CommonLaunchHandler.java:136) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.clientService(CommonLaunchHandler.java:124) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonClientLaunchHandler.runService(CommonClientLaunchHandler.java:32) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.lambda$launchService$4(CommonLaunchHandler.java:118) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandlerDecorator.launch(LaunchServiceHandlerDecorator.java:30) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:53) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:71) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.Launcher.run(Launcher.java:103) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.Launcher.main(Launcher.java:74) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:26) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:23) [modlauncher-11.0.5.jar%23112!/:?] {}
	at cpw.mods.bootstraplauncher@2.0.2/cpw.mods.bootstraplauncher.BootstrapLauncher.run(BootstrapLauncher.java:210) [bootstraplauncher-2.0.2.jar:?] {}
	at cpw.mods.bootstraplauncher@2.0.2/cpw.mods.bootstraplauncher.BootstrapLauncher.main(BootstrapLauncher.java:69) [bootstraplauncher-2.0.2.jar:?] {}


A detailed walkthrough of the error, its code path and all known details is as follows:
---------------------------------------------------------------------------------------

-- Head --
Thread: Render thread
Stacktrace:
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.model.geom.EntityModelSet.bakeLayer(EntityModelSet.java:17) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,re:classloading,pl:accesstransformer:B,pl:mixin:A}
	at TRANSFORMER/twilightforest@4.7.3196/twilightforest.client.ISTER.<init>(ISTER.java:102) ~[twilightforest-1.21.1-4.7.3196-universal.jar%23771!/:4.7.3196] {re:classloading}
	at MC-BOOTSTRAP/com.google.common@32.1.2-jre/com.google.common.base.Suppliers$NonSerializableMemoizingSupplier.get(Suppliers.java:181) ~[guava-32.1.2-jre.jar%23135!/:?] {}
	at TRANSFORMER/twilightforest@4.7.3196/twilightforest.client.event.ClientEvents.handleGameBootup(ClientEvents.java:119) ~[twilightforest-1.21.1-4.7.3196-universal.jar%23771!/:4.7.3196] {re:classloading}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.ConsumerEventHandler.invoke(ConsumerEventHandler.java:27) ~[bus-8.0.5.jar%23110!/:?] {}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.EventBus.post(EventBus.java:360) ~[bus-8.0.5.jar%23110!/:?] {}
	at MC-BOOTSTRAP/net.neoforged.bus/net.neoforged.bus.EventBus.post(EventBus.java:328) ~[bus-8.0.5.jar%23110!/:?] {}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.rebuildWidgets(Screen.java:337) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.repositionElements(Screen.java:440) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.gui.screens.Screen.resize(Screen.java:446) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenMixin from mod fabric_screen_api_v1,pl:mixin:APP:keybindspurger.mixins.json:IScreenAccessor from mod keybindspurger,pl:mixin:APP:balm.neoforge.mixins.json:ScreenAccessor from mod balm,pl:mixin:APP:fabric-screen-api-v1.mixins.json:ScreenAccessor from mod fabric_screen_api_v1,pl:mixin:APP:cumulus_menus.mixins.json:client.accessor.ScreenAccessor from mod cumulus_menus,pl:mixin:APP:ponder-common.mixins.json:client.accessor.ScreenAccessor from mod ponder,pl:mixin:APP:aether.mixins.json:client.accessor.ScreenAccessor from mod aether,pl:mixin:APP:relics.mixins.json:ScreenMixin from mod relics,pl:mixin:APP:nuggets.mixins.json:ScreenAccessor from mod nuggets,pl:mixin:APP:patchouli_xplat.mixins.json:client.AccessorScreen from mod patchouli,pl:mixin:APP:nerb-common.mixins.json:ScreenMixin from mod nerb,pl:mixin:APP:owo.mixins.json:ScreenAccessor from mod owo,pl:mixin:APP:owo.mixins.json:ui.ScreenMixin from mod owo,pl:mixin:APP:octolib-common.mixins.json:ScreenMixin from mod octolib,pl:mixin:APP:trender.mixins.json:client.ScreenAccessor from mod trender,pl:mixin:APP:journeymap.mixins.json:client.ScreenAccessor from mod journeymap,pl:mixin:APP:mixins.extendedae.json:MixinScreen from mod extendedae,pl:mixin:APP:rrls-forge.mixins.json:ScreenMixin from mod rrls,pl:mixin:APP:create.mixins.json:compat.xaeros.XaeroPauseScreenOverrideMixin from mod create,pl:mixin:APP:ae2.mixins.json:WrappedGenericStackTooltipModIdMixin from mod ae2,pl:mixin:APP:owo.mixins.json:ui.layers.ScreenMixin from mod owo,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.resizeDisplay(Minecraft.java:1326) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/com.mojang.blaze3d.platform.Window.onFramebufferResize(Window.java:251) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:APP:mixins.sodiumextras.json:impl.borderless.BorderlessWindowMixin from mod sodiumextras,pl:mixin:APP:mixins.sodiumextras.json:impl.borderless.accessors.MainWindowAccessor from mod sodiumextras,pl:mixin:APP:sodium-common.mixins.json:core.WindowMixin from mod sodium,pl:mixin:APP:sodium-common.mixins.json:workarounds.context_creation.WindowMixin from mod sodium,pl:mixin:APP:immediatelyfast-common.mixins.json:core.MixinWindow from mod immediatelyfast,pl:mixin:APP:relics.mixins.json:WindowMixin from mod relics,pl:mixin:APP:chloride.mixin.json:BorderlessMixin$WindowMixin from mod chloride,pl:mixin:A,pl:runtimedistcleaner:A}
	at MC-BOOTSTRAP/org.lwjgl.glfw@3.3.3+5/org.lwjgl.glfw.GLFWFramebufferSizeCallbackI.callback(GLFWFramebufferSizeCallbackI.java:44) ~[lwjgl-glfw-3.3.3.jar%23173!/:build 5] {}
	at MC-BOOTSTRAP/org.lwjgl@3.3.3+5/org.lwjgl.system.JNI.invokeV(Native Method) ~[lwjgl-3.3.3.jar%23185!/:build 5] {}
	at MC-BOOTSTRAP/org.lwjgl.glfw@3.3.3+5/org.lwjgl.glfw.GLFW.glfwWaitEventsTimeout(GLFW.java:3509) ~[lwjgl-glfw-3.3.3.jar%23173!/:build 5] {re:mixin}
-- Uptime --
Details:
	JVM uptime: 38.469s
	Wall uptime: 21.131s
	High-res time: 35.907s
	Client ticks: 131 ticks / 6.550s
Stacktrace:
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.fillReport(Minecraft.java:2394) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.emergencySaveAndCrash(Minecraft.java:868) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.Minecraft.run(Minecraft.java:828) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:accesstransformer:B,pl:runtimedistcleaner:A,re:classloading,pl:accesstransformer:B,pl:mixin:A,pl:runtimedistcleaner:A}
	at TRANSFORMER/minecraft@1.21.1/net.minecraft.client.main.Main.main(Main.java:230) ~[client-1.21.1-20240808.144430-srg.jar%23485!/:?] {re:mixin,pl:runtimedistcleaner:A,re:classloading,pl:mixin:APP:cryonicconfig.mixins.json:client.MainMixin from mod cryonicconfig,pl:mixin:A,pl:runtimedistcleaner:A}
	at java.base/jdk.internal.reflect.DirectMethodHandleAccessor.invoke(DirectMethodHandleAccessor.java:103) ~[?:?] {}
	at java.base/java.lang.reflect.Method.invoke(Method.java:580) ~[?:?] {re:mixin}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.runTarget(CommonLaunchHandler.java:136) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.clientService(CommonLaunchHandler.java:124) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonClientLaunchHandler.runService(CommonClientLaunchHandler.java:32) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/fml_loader@4.0.42/net.neoforged.fml.loading.targets.CommonLaunchHandler.lambda$launchService$4(CommonLaunchHandler.java:118) ~[loader-4.0.42.jar%23107!/:4.0] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandlerDecorator.launch(LaunchServiceHandlerDecorator.java:30) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:53) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.LaunchServiceHandler.launch(LaunchServiceHandler.java:71) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.Launcher.run(Launcher.java:103) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.Launcher.main(Launcher.java:74) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:26) [modlauncher-11.0.5.jar%23112!/:?] {}
	at MC-BOOTSTRAP/cpw.mods.modlauncher@11.0.5/cpw.mods.modlauncher.BootstrapLaunchConsumer.accept(BootstrapLaunchConsumer.java:23) [modlauncher-11.0.5.jar%23112!/:?] {}
	at cpw.mods.bootstraplauncher@2.0.2/cpw.mods.bootstraplauncher.BootstrapLauncher.run(BootstrapLauncher.java:210) [bootstraplauncher-2.0.2.jar:?] {}
	at cpw.mods.bootstraplauncher@2.0.2/cpw.mods.bootstraplauncher.BootstrapLauncher.main(BootstrapLauncher.java:69) [bootstraplauncher-2.0.2.jar:?] {}


-- Last reload --
Details:
	Reload number: 1
	Reload reason: initial
	Finished: No
	Packs: vanilla, fabric, mod_resources, mod/sodium, mod/saturn, mod/supermartijn642configlib, mod/sodiumextras, mod/simplemagnets, mod/playeranimator, mod/saeculariacaudices, mod/integratedterminals,integratedterminalscompat, mod/fabric_rendering_fluids_v1, mod/enderio_base, mod/mcwwindows, mod/projecte, mod/mffs, mod/modnametooltip, mod/ironjetpacks, mod/neat, mod/endercore, mod/forgeendertech, mod/fabric_convention_tags_v1, mod/nanny, mod/neoforge, mod/modernfix, mod/fabric_convention_tags_v2, mod/fabric_block_view_api_v2, mod/fabric_command_api_v2, mod/powah, mod/maxhealthfix, mod/rangedpumps, mod/universalgrid, mod/keybindspurger, mod/ae2importexportcard, mod/forgivingvoid, mod/balm, mod/fabric_screen_api_v1, mod/prickle, mod/jeresources, mod/structure_layout_optimizer, mod/cloth_config, mod/supplementaries, mod/refinedstorage, mod/durabilitytooltip, mod/novillagerdm, mod/lmft, mod/alltheores, mod/glodium, mod/industrialforegoing, mod/tickwands, mod/torchmaster, mod/fabric_game_rule_api_v1, mod/explorify, mod/ironfurnaces, mod/transparent, mod/silentgear, mod/supermartijn642corelib, mod/resourcefulconfig, mod/reeses_sodium_options, mod/curios, mod/searchables, mod/measurements, mod/icarus, mod/fabric_entity_events_v1, mod/extrastorage, mod/accessories, mod/worldedit, mod/sodiumoptionsmodcompat, mod/cumulus_menus, mod/conditional_mixin, mod/apothic_enchanting, mod/transition, mod/fabric_rendering_data_attachment_v1, mod/nitrogen_internals, mod/jadeaddons, mod/codechickenlib, mod/fastleafdecay, mod/enderio_machines, mod/journeymap_api, mod/crafting_on_a_stick, mod/fabric_client_tags_api_v1, mod/ae2jeiintegration, mod/smartbrainlib, mod/mowziesmobs, mod/doubledoors, mod/rechiseled, mod/fabric_model_loading_api_v1, mod/jei, mod/everlastingabilities, mod/visualworkbench, mod/lithium, mod/attributefix, mod/fabric_screen_handler_api_v1, mod/flerovium, mod/mekanism, mod/caelus, mod/fabric_rendering_v1, mod/fabric_renderer_indigo, mod/fallingleaves, mod/fastasyncworldsave, mod/naturescompass, mod/compactmachines, mod/glitchcore, mod/sereneseasons, mod/farmingforblockheads, mod/pneumaticcraft, mod/craterlib, mod/snowundertrees, mod/fusion, mod/simple_snowy_fix, mod/extradisks, mod/edivadlib, mod/fabric_particles_v1, mod/infernalmobs, mod/ironchest, mod/integratedcrafting, mod/dungeons_arise, mod/zerocore, mod/smoothchunk, mod/scena, mod/aethersteel, mod/fabric_api_base, mod/terrablender, mod/biomesoplenty, mod/mousetweaks, mod/immersiveengineering, mod/nochatreports, mod/allthemodium, mod/ohthetreesyoullgrow, mod/does_it_tick, mod/alltheleaks, mod/spectrelib, mod/cleanswing, mod/adlods, mod/fabric_block_api_v1, mod/corgilib, mod/ding, mod/fabric_resource_conditions_api_v1, mod/fastpaintings, mod/aeroblender, mod/kotlinforforge, mod/pipez, mod/flywheel, mod/ponder, mod/integrateddynamics,integrateddynamicscompat, mod/itemcollectors, mod/fabric_item_group_api_v1, mod/gravestone, mod/bhc, mod/polymorph, mod/almostunified, mod/entityculling, mod/backpacked, mod/enderio_conduits_modded, mod/wits, mod/fabric_registry_sync_v0, mod/pickletweaks, mod/immediatelyfast, mod/lambdynlights_api, mod/structory_towers, mod/fabric_recipe_api_v1, mod/connectedglass, mod/lootr, mod/fabric_object_builder_api_v1, mod/occultism, mod/puzzleslib, mod/aquaculture, mod/refinedstorage_jei_integration, mod/fabric_sound_api_v1, mod/fabric_message_api_v1, mod/extremesoundmuffler, mod/cosmeticarmorreworked, mod/configurable, mod/xpbook, mod/cristellib, mod/totw_modded, mod/cyclopscore, mod/aether_enhanced_extinguishing, mod/kuma_api, mod/fabric_renderer_api_v1, mod/refinedstorage_quartz_arsenal, mod/netherportalfix, mod/geckolib, mod/ars_nouveau, mod/recipeessentials, mod/fabric_item_api_v1, mod/aether, mod/deep_aether, mod/connectivity, mod/incendium, mod/sophisticatedcore, mod/gpumemleakfix, mod/bowinfinityfix, mod/structureessentials, mod/cookingforblockheads, mod/controlling, mod/placebo, mod/wstweaks, mod/apothic_attributes, mod/fastitemframes, mod/fabric_data_attachment_api_v1, mod/redirected, mod/bookshelf, mod/sophisticatedbackpacks, mod/relics, mod/nuggets, mod/mekanismgenerators, mod/sodiumoptionsapi, mod/refinedstorage_mekanism_integration, mod/explore_ruins_aether, mod/dummmmmmy, mod/fzzy_config, mod/particle_core, mod/fabric_api, mod/fabric_content_registries_v0, mod/twilightforest, mod/mob_grinding_utils, mod/rsinfinitybooster, mod/arseng, mod/farmersdelight, mod/entity_model_features, mod/entity_texture_features, mod/fastipping, mod/entangled, mod/commoncapabilities, mod/fabric_api_lookup_api_v1, mod/colorfulhearts, mod/modelfix, mod/actuallyadditions, mod/memorysettings, mod/patchouli, mod/suppsquared, mod/collective, mod/oreexcavation, mod/tiab, mod/integratedtunnels,integratedtunnelscompat, mod/elevatorid, mod/mekanismtools, mod/architectury, mod/nerb, mod/ftblibrary, mod/jamlib, mod/rightclickharvest, mod/wands, mod/ftbteams, mod/ftbquests, mod/fabric_loot_api_v2, mod/fabric_loot_api_v3, mod/moreoverlays, mod/cupboard, mod/bigreactors, mod/trashcans, mod/fabric_networking_api_v1, mod/framework, mod/bwncr, mod/polylib, mod/shrink, mod/t_and_t, mod/fabric_lifecycle_events_v1, mod/fabric_key_binding_api_v1, mod/betteradvancements, mod/fabric_transfer_api_v1, mod/inventorysorter, mod/vuc, mod/owo, mod/cucumber, mod/treasuredistance, mod/asyncparticles, mod/pamhc2trees, mod/blueflame, mod/octolib, mod/ash_api, mod/biomeswevegone, mod/commonnetworking, mod/simplerpc, mod/fabric_resource_loader_v0, mod/trender, mod/create, mod/framedblocks, mod/chloride, mod/waystones, mod/sparkweave, mod/fastsuite, mod/clumps, mod/journeymap, mod/comforts, mod/artifacts, mod/configured, mod/dungeoncrawl, mod/charginggadgets, mod/ftbbackups2, mod/mcjtylib, mod/rftoolsbase, mod/xnet, mod/rftoolsdim, mod/notenoughwands, mod/rftoolspower, mod/rftoolsbuilder, mod/rftoolsstorage, mod/rftoolscontrol, mod/guideme, mod/ichunutil, mod/txnilib, mod/enderstorage, mod/akashictome, mod/ftbchunks, mod/toofast, mod/fabric_transitive_access_wideners_v1, mod/brandonscore, mod/draconicevolution, mod/mysticalagriculture, mod/mysticalagradditions, mod/craftingtweaks, mod/rftoolsutility, mod/enchdesc, mod/moonlight, mod/apothic_spawners, mod/apotheosis, mod/enderio_conduits, mod/toolbelt, mod/titanium, mod/regions_unexplored, mod/silentlib, mod/fabric_blockrenderlayer_v1, mod/jade, mod/ae2, mod/aeinfinitybooster, mod/extendedae, mod/megacells, mod/ae2addonlib, mod/merequester, mod/advanced_ae, mod/ae2wtlib_api, mod/ae2things, mod/enderio_armory, mod/chunkactivitytracker, mod/enderio, mod/brutalbosses, mod/reliquary, mod/polyeng, mod/fabric_gametest_api_v1, mod/storagedrawers, mod/fluxnetworks, mod/immersive_paintings, mod/irons_spellbooks, mod/jei_mekanism_multiblocks, mod/betterchunkloading, mod/inventoryhud, mod/fabric_biome_api_v1, mod/cognition, mod/buildinggadgets2, mod/modonomicon, mod/cryonicconfig, mod/worldstripper, mod/chisel, mod/ferritecore, mod/solcarrot, mod/functionalstorage, mod/modularrouters, mod/rrls, mod/packetfixer, mod/badoptimizations, mod/expandability, mod/chiselsandbits, mod/overloadedarmorbar, mod/fabric_data_generation_api_v1, mod/fabric_events_interaction_v0, moonlight:merged_pack, chiselsandbits-core, visualworkbench:default_block_models

-- System Details --
Details:
	Minecraft Version: 1.21.1
	Minecraft Version ID: 1.21.1
	Operating System: Windows 10 (amd64) version 10.0
	Java Version: 21.0.7, Microsoft
	Java VM Version: OpenJDK 64-Bit Server VM (mixed mode), Microsoft
	Memory: 1228304992 bytes (1171 MiB) / 3279945728 bytes (3128 MiB) up to 8589934592 bytes (8192 MiB)
	CPUs: 32
	Processor Vendor: AuthenticAMD
	Processor Name: AMD Ryzen 9 5950X 16-Core Processor            
	Identifier: AuthenticAMD Family 25 Model 33 Stepping 2
	Microarchitecture: Zen 3
	Frequency (GHz): 3.40
	Number of physical packages: 1
	Number of physical CPUs: 16
	Number of logical CPUs: 32
	Graphics card #0 name: NVIDIA GeForce RTX 3080
	Graphics card #0 vendor: NVIDIA
	Graphics card #0 VRAM (MiB): 10240.00
	Graphics card #0 deviceId: VideoController1
	Graphics card #0 versionInfo: 32.0.15.9144
	Graphics card #1 name: AMD Radeon RX 5700 XT
	Graphics card #1 vendor: Advanced Micro Devices, Inc.
	Graphics card #1 VRAM (MiB): 8176.00
	Graphics card #1 deviceId: VideoController2
	Graphics card #1 versionInfo: 31.0.23013.14001
	Graphics card #2 name: AMD Radeon RX 5700 XT
	Graphics card #2 vendor: Advanced Micro Devices, Inc.
	Graphics card #2 VRAM (MiB): 8176.00
	Graphics card #2 deviceId: VideoController3
	Graphics card #2 versionInfo: 31.0.23013.14001
	Memory slot #0 capacity (MiB): 16384.00
	Memory slot #0 clockSpeed (GHz): 4.00
	Memory slot #0 type: DDR4
	Memory slot #1 capacity (MiB): 16384.00
	Memory slot #1 clockSpeed (GHz): 4.00
	Memory slot #1 type: DDR4
	Memory slot #2 capacity (MiB): 16384.00
	Memory slot #2 clockSpeed (GHz): 4.00
	Memory slot #2 type: DDR4
	Memory slot #3 capacity (MiB): 16384.00
	Memory slot #3 clockSpeed (GHz): 4.00
	Memory slot #3 type: DDR4
	Virtual memory max (MiB): 98211.68
	Virtual memory used (MiB): 25113.72
	Swap memory total (MiB): 32768.00
	Swap memory used (MiB): 3354.31
	Space in storage for jna.tmpdir (MiB): available: 172925.33, total: 953852.00
	Space in storage for org.lwjgl.system.SharedLibraryExtractPath (MiB): available: 172925.33, total: 953852.00
	Space in storage for io.netty.native.workdir (MiB): available: 172925.33, total: 953852.00
	Space in storage for java.io.tmpdir (MiB): available: 112919.08, total: 953203.19
	Space in storage for workdir (MiB): available: 172925.33, total: 953852.00
	JVM Flags: 4 total; -XX:HeapDumpPath=MojangTricksIntelDriversForPerformance_javaw.exe_minecraft.exe.heapdump -Xss1M -Xmx8192m -Xms256m
	Launched Version: neoforge-21.1.216
	Launcher name: minecraft-launcher
	Backend library: LWJGL version 3.3.3+5
	Backend API: NVIDIA GeForce RTX 3080/PCIe/SSE2 GL version 4.6.0 NVIDIA 591.44, NVIDIA Corporation
	Window size: 1920x1057
	GFLW Platform: win32
	GL Caps: Using framebuffer using OpenGL 3.2
	GL debug messages: 
	Is Modded: Definitely; Client brand changed to 'neoforge'
	Universe: 400921fb54442d18
	Type: Client (map_client.txt)
	Graphics mode: fancy
	Render Distance: 20/20 chunks
	Resource Packs: vanilla, fabric, mod_resources, mod/sodium, mod/saturn, mod/supermartijn642configlib, mod/sodiumextras (incompatible), mod/simplemagnets, mod/playeranimator, mod/saeculariacaudices, mod/integratedterminals,integratedterminalscompat (incompatible), mod/fabric_rendering_fluids_v1, mod/enderio_base, mod/mcwwindows, mod/projecte, mod/mffs, mod/modnametooltip (incompatible), mod/ironjetpacks, mod/neat (incompatible), mod/endercore, mod/forgeendertech, mod/fabric_convention_tags_v1, mod/nanny, mod/neoforge, mod/modernfix (incompatible), mod/fabric_convention_tags_v2, mod/fabric_block_view_api_v2, mod/fabric_command_api_v2, mod/powah (incompatible), mod/maxhealthfix (incompatible), mod/rangedpumps (incompatible), mod/universalgrid, mod/keybindspurger, mod/ae2importexportcard, mod/forgivingvoid (incompatible), mod/balm (incompatible), mod/fabric_screen_api_v1, mod/prickle (incompatible), mod/jeresources (incompatible), mod/structure_layout_optimizer, mod/cloth_config (incompatible), mod/supplementaries (incompatible), mod/refinedstorage, mod/durabilitytooltip, mod/novillagerdm, mod/lmft (incompatible), mod/alltheores (incompatible), mod/glodium (incompatible), mod/industrialforegoing (incompatible), mod/tickwands, mod/torchmaster (incompatible), mod/fabric_game_rule_api_v1, mod/explorify, mod/ironfurnaces, mod/transparent, mod/silentgear, mod/supermartijn642corelib, mod/resourcefulconfig, mod/reeses_sodium_options, mod/curios (incompatible), mod/searchables (incompatible), mod/measurements, mod/icarus, mod/fabric_entity_events_v1, mod/extrastorage, mod/accessories (incompatible), mod/worldedit (incompatible), mod/sodiumoptionsmodcompat (incompatible), mod/cumulus_menus, mod/conditional_mixin (incompatible), mod/apothic_enchanting, mod/transition, mod/fabric_rendering_data_attachment_v1, mod/nitrogen_internals, mod/jadeaddons (incompatible), mod/codechickenlib (incompatible), mod/fastleafdecay, mod/enderio_machines, mod/journeymap_api (incompatible), mod/crafting_on_a_stick (incompatible), mod/fabric_client_tags_api_v1, mod/ae2jeiintegration, mod/smartbrainlib (incompatible), mod/mowziesmobs (incompatible), mod/doubledoors (incompatible), mod/rechiseled, mod/fabric_model_loading_api_v1, mod/jei (incompatible), mod/everlastingabilities (incompatible), mod/visualworkbench, mod/lithium, mod/attributefix (incompatible), mod/fabric_screen_handler_api_v1, mod/flerovium (incompatible), mod/mekanism, mod/caelus (incompatible), mod/fabric_rendering_v1, mod/fabric_renderer_indigo, mod/fallingleaves (incompatible), mod/fastasyncworldsave (incompatible), mod/naturescompass, mod/compactmachines (incompatible), mod/glitchcore (incompatible), mod/sereneseasons (incompatible), mod/farmingforblockheads (incompatible), mod/pneumaticcraft, mod/craterlib (incompatible), mod/snowundertrees, mod/fusion, mod/simple_snowy_fix (incompatible), mod/extradisks, mod/edivadlib, mod/fabric_particles_v1, mod/infernalmobs (incompatible), mod/ironchest, mod/integratedcrafting (incompatible), mod/dungeons_arise, mod/zerocore (incompatible), mod/smoothchunk (incompatible), mod/scena (incompatible), mod/aethersteel (incompatible), mod/fabric_api_base, mod/terrablender (incompatible), mod/biomesoplenty, mod/mousetweaks (incompatible), mod/immersiveengineering (incompatible), mod/nochatreports, mod/allthemodium (incompatible), mod/ohthetreesyoullgrow, mod/does_it_tick (incompatible), mod/alltheleaks, mod/spectrelib (incompatible), mod/cleanswing, mod/adlods, mod/fabric_block_api_v1, mod/corgilib, mod/ding, mod/fabric_resource_conditions_api_v1, mod/fastpaintings (incompatible), mod/aeroblender (incompatible), mod/kotlinforforge (incompatible), mod/pipez, mod/flywheel, mod/ponder (incompatible), mod/integrateddynamics,integrateddynamicscompat (incompatible), mod/itemcollectors, mod/fabric_item_group_api_v1, mod/gravestone, mod/bhc, mod/polymorph (incompatible), mod/almostunified, mod/entityculling, mod/backpacked (incompatible), mod/enderio_conduits_modded, mod/wits, mod/fabric_registry_sync_v0, mod/pickletweaks, mod/immediatelyfast (incompatible), mod/lambdynlights_api, mod/structory_towers (incompatible), mod/fabric_recipe_api_v1, mod/connectedglass, mod/lootr, mod/fabric_object_builder_api_v1, mod/occultism, mod/puzzleslib, mod/aquaculture (incompatible), mod/refinedstorage_jei_integration (incompatible), mod/fabric_sound_api_v1, mod/fabric_message_api_v1, mod/extremesoundmuffler (incompatible), mod/cosmeticarmorreworked (incompatible), mod/configurable, mod/xpbook, mod/cristellib, mod/totw_modded, mod/cyclopscore (incompatible), mod/aether_enhanced_extinguishing, mod/kuma_api (incompatible), mod/fabric_renderer_api_v1, mod/refinedstorage_quartz_arsenal, mod/netherportalfix (incompatible), mod/geckolib, mod/ars_nouveau (incompatible), mod/recipeessentials (incompatible), mod/fabric_item_api_v1, mod/aether, mod/deep_aether (incompatible), mod/connectivity (incompatible), mod/incendium (incompatible), mod/sophisticatedcore (incompatible), mod/gpumemleakfix (incompatible), mod/bowinfinityfix, mod/structureessentials (incompatible), mod/cookingforblockheads (incompatible), mod/controlling (incompatible), mod/placebo, mod/wstweaks, mod/apothic_attributes, mod/fastitemframes, mod/fabric_data_attachment_api_v1, mod/redirected (incompatible), mod/bookshelf (incompatible), mod/sophisticatedbackpacks (incompatible), mod/relics (incompatible), mod/nuggets (incompatible), mod/mekanismgenerators, mod/sodiumoptionsapi (incompatible), mod/refinedstorage_mekanism_integration (incompatible), mod/explore_ruins_aether (incompatible), mod/dummmmmmy (incompatible), mod/fzzy_config, mod/particle_core, mod/fabric_api, mod/fabric_content_registries_v0, mod/twilightforest, mod/mob_grinding_utils (incompatible), mod/rsinfinitybooster (incompatible), mod/arseng, mod/farmersdelight (incompatible), mod/entity_model_features (incompatible), mod/entity_texture_features (incompatible), mod/fastipping (incompatible), mod/entangled, mod/commoncapabilities (incompatible), mod/fabric_api_lookup_api_v1, mod/colorfulhearts (incompatible), mod/modelfix (incompatible), mod/actuallyadditions, mod/memorysettings (incompatible), mod/patchouli (incompatible), mod/suppsquared (incompatible), mod/collective (incompatible), mod/oreexcavation (incompatible), mod/tiab (incompatible), mod/integratedtunnels,integratedtunnelscompat (incompatible), mod/elevatorid, mod/mekanismtools, mod/architectury (incompatible), mod/nerb, mod/ftblibrary (incompatible), mod/jamlib (incompatible), mod/rightclickharvest (incompatible), mod/wands, mod/ftbteams (incompatible), mod/ftbquests (incompatible), mod/fabric_loot_api_v2, mod/fabric_loot_api_v3, mod/moreoverlays (incompatible), mod/cupboard (incompatible), mod/bigreactors (incompatible), mod/trashcans, mod/fabric_networking_api_v1, mod/framework (incompatible), mod/bwncr, mod/polylib (incompatible), mod/shrink (incompatible), mod/t_and_t, mod/fabric_lifecycle_events_v1, mod/fabric_key_binding_api_v1, mod/betteradvancements (incompatible), mod/fabric_transfer_api_v1, mod/inventorysorter (incompatible), mod/vuc (incompatible), mod/owo, mod/cucumber, mod/treasuredistance, mod/asyncparticles (incompatible), mod/pamhc2trees, mod/blueflame (incompatible), mod/octolib, mod/ash_api, mod/biomeswevegone, mod/commonnetworking (incompatible), mod/simplerpc (incompatible), mod/fabric_resource_loader_v0, mod/trender, mod/create (incompatible), mod/framedblocks, mod/chloride, mod/waystones (incompatible), mod/sparkweave, mod/fastsuite, mod/clumps (incompatible), mod/journeymap (incompatible), mod/comforts (incompatible), mod/artifacts, mod/configured, mod/dungeoncrawl (incompatible), mod/charginggadgets (incompatible), mod/ftbbackups2 (incompatible), mod/mcjtylib, mod/rftoolsbase, mod/xnet, mod/rftoolsdim, mod/notenoughwands, mod/rftoolspower, mod/rftoolsbuilder, mod/rftoolsstorage, mod/rftoolscontrol, mod/guideme, mod/ichunutil, mod/txnilib (incompatible), mod/enderstorage (incompatible), mod/akashictome (incompatible), mod/ftbchunks (incompatible), mod/toofast (incompatible), mod/fabric_transitive_access_wideners_v1, mod/brandonscore (incompatible), mod/draconicevolution (incompatible), mod/mysticalagriculture, mod/mysticalagradditions, mod/craftingtweaks (incompatible), mod/rftoolsutility, mod/enchdesc (incompatible), mod/moonlight (incompatible), mod/apothic_spawners, mod/apotheosis, mod/enderio_conduits, mod/toolbelt (incompatible), mod/titanium, mod/regions_unexplored (incompatible), mod/silentlib (incompatible), mod/fabric_blockrenderlayer_v1, mod/jade (incompatible), mod/ae2 (incompatible), mod/aeinfinitybooster (incompatible), mod/extendedae (incompatible), mod/megacells, mod/ae2addonlib, mod/merequester, mod/advanced_ae (incompatible), mod/ae2wtlib_api, mod/ae2things (incompatible), mod/enderio_armory, mod/chunkactivitytracker (incompatible), mod/enderio, mod/brutalbosses (incompatible), mod/reliquary (incompatible), mod/polyeng, mod/fabric_gametest_api_v1, mod/storagedrawers, mod/fluxnetworks (incompatible), mod/immersive_paintings (incompatible), mod/irons_spellbooks, mod/jei_mekanism_multiblocks (incompatible), mod/betterchunkloading (incompatible), mod/inventoryhud, mod/fabric_biome_api_v1, mod/cognition (incompatible), mod/buildinggadgets2 (incompatible), mod/modonomicon, mod/cryonicconfig, mod/worldstripper (incompatible), mod/chisel (incompatible), mod/ferritecore (incompatible), mod/solcarrot, mod/functionalstorage (incompatible), mod/modularrouters, mod/rrls, mod/packetfixer (incompatible), mod/badoptimizations (incompatible), mod/expandability, mod/chiselsandbits (incompatible), mod/overloadedarmorbar, mod/fabric_data_generation_api_v1, mod/fabric_events_interaction_v0, moonlight:merged_pack, chiselsandbits-core (incompatible), visualworkbench:default_block_models
	Current Language: en_us
	Locale: en_US
	System encoding: Cp1252
	File encoding: UTF-8
	CPU: 32x AMD Ryzen 9 5950X 16-Core Processor 
	ModLauncher: 11.0.5+main.901c6ea8
	ModLauncher launch target: forgeclient
	ModLauncher services: 
		sponge-mixin-0.15.2+mixin.0.8.7.jar mixin PLUGINSERVICE 
		loader-4.0.42.jar slf4jfixer PLUGINSERVICE 
		loader-4.0.42.jar runtime_enum_extender PLUGINSERVICE 
		at-modlauncher-10.0.1.jar accesstransformer PLUGINSERVICE 
		loader-4.0.42.jar runtimedistcleaner PLUGINSERVICE 
		modlauncher-11.0.5.jar mixin TRANSFORMATIONSERVICE 
		modlauncher-11.0.5.jar fml TRANSFORMATIONSERVICE 
	FML Language Providers: 
		kotlinforforge@5.10.0
		__fabric_loader_bootstrap@2.5.29+0.16.0+1.21
		kotori_scala@3.7.1-build-11
		javafml@4.0
		lowcodefml@4.0
		minecraft@4.0
	Mod List: 
		accessories-neoforge-1.1.0-beta.52+1.21.1.jar     |Accessories                   |accessories                   |1.1.0-beta.52+1.21.1|Manifest: NOSIGNATURE
		actuallyadditions-1.3.22+mc1.21.1.jar             |Actually Additions            |actuallyadditions             |1.3.22              |Manifest: NOSIGNATURE
		AdvancedAE-1.6.7-1.21.1.jar                       |Advanced AE                   |advanced_ae                   |1.6.7-1.21.1        |Manifest: NOSIGNATURE
		ae2importexportcard-1.21.1-1.4.1.jar              |AE2 Import Export Card        |ae2importexportcard           |1.21.1-1.4.1        |Manifest: NOSIGNATURE
		ae2jeiintegration-1.2.0.jar                       |AE2 JEI Integration           |ae2jeiintegration             |1.2.0               |Manifest: NOSIGNATURE
		AE2-Things-1.4.2-beta.jar                         |AE2 Things                    |ae2things                     |1.4.2-beta          |Manifest: NOSIGNATURE
		ae2addonlib-1.0.3-1.21.1.jar                      |AE2AddonLib                   |ae2addonlib                   |1.0.3-1.21.1        |Manifest: NOSIGNATURE
		ae2wtlib_api-19.2.5.jar                           |AE2WTLib API                  |ae2wtlib_api                  |19.2.5              |Manifest: NOSIGNATURE
		aeinfinitybooster-neoforge-1.21.1-1.0.0.52.jar    |AEInfinityBooster             |aeinfinitybooster             |1.21.1-1.0.0.52     |Manifest: NOSIGNATURE
		aeroblender-1.21.1-1.0.0-neoforge.jar             |AeroBlender                   |aeroblender                   |1.0.0               |Manifest: NOSIGNATURE
		Aethersteel-v5.6-1.21.1.jar                       |Aethersteel                   |aethersteel                   |5.6                 |Manifest: NOSIGNATURE
		AkashicTome-1.8-29.jar                            |Akashic Tome                  |akashictome                   |1.8-29              |Manifest: NOSIGNATURE
		alltheleaks-1.1.4+1.21.1-neoforge.jar             |All The Leaks                 |alltheleaks                   |1.1.4+1.21.1-neoforg|Manifest: NOSIGNATURE
		allthemodium-2.9.5_mc_1.21.1.jar                  |Allthemodium                  |allthemodium                  |2.9.5               |Manifest: NOSIGNATURE
		alltheores-3.1.8_neoforge_1.21.1.jar              |AllTheOres                    |alltheores                    |3.1.8               |Manifest: NOSIGNATURE
		almostunified-neoforge-1.21.1-1.3.0.jar           |AlmostUnified                 |almostunified                 |1.21.1-1.3.0        |Manifest: NOSIGNATURE
		Apotheosis-1.21.1-8.4.1.jar                       |Apotheosis                    |apotheosis                    |8.4.1               |Manifest: NOSIGNATURE
		ApothicAttributes-1.21.1-2.9.0.jar                |Apothic Attributes            |apothic_attributes            |2.9.0               |Manifest: NOSIGNATURE
		ApothicEnchanting-1.21.1-1.5.0.jar                |Apothic Enchanting            |apothic_enchanting            |1.5.0               |Manifest: NOSIGNATURE
		ApothicSpawners-1.21.1-1.3.2.jar                  |Apothic Spawners              |apothic_spawners              |1.3.2               |Manifest: NOSIGNATURE
		appliedenergistics2-19.2.17.jar                   |Applied Energistics 2         |ae2                           |19.2.17             |Manifest: NOSIGNATURE
		Aquaculture-1.21.1-2.7.16.jar                     |Aquaculture 2                 |aquaculture                   |2.7.16              |Manifest: NOSIGNATURE
		architectury-13.0.8-neoforge.jar                  |Architectury                  |architectury                  |13.0.8              |Manifest: NOSIGNATURE
		ars_nouveau-1.21.1-5.10.6.jar                     |Ars Nouveau                   |ars_nouveau                   |5.10.6              |Manifest: NOSIGNATURE
		arseng-2.1.1-beta.jar                             |Ars Énergistique              |arseng                        |2.1.1-beta          |Manifest: NOSIGNATURE
		artifacts-neoforge-13.1.0.jar                     |Artifacts                     |artifacts                     |13.1.0              |Manifest: NOSIGNATURE
		ash_api-neoforge-21.1.1.jar                       |Ash API                       |ash_api                       |21.1.1              |Manifest: NOSIGNATURE
		AsyncParticles-3.4.0-beta.1+1.21.1.jar            |AsyncParticles                |asyncparticles                |3.4.0-beta.1        |Manifest: NOSIGNATURE
		attributefix-neoforge-1.21.1-21.1.3.jar           |AttributeFix                  |attributefix                  |21.1.3              |Manifest: NOSIGNATURE
		backpacked-neoforge-1.21.1-3.0.0-beta.18-signed.ja|Backpacked                    |backpacked                    |3.0.0-beta.18       |Manifest: NOSIGNATURE
		bwncr-neoforge-1.21.1-3.20.3.jar                  |Bad Wither No Cookie Reloaded |bwncr                         |3.20.3              |Manifest: NOSIGNATURE
		BadOptimizations-2.4.0-1.21.1.jar                 |BadOptimizations              |badoptimizations              |2.4.0               |Manifest: NOSIGNATURE
		balm-neoforge-1.21.1-21.0.55.jar                  |Balm                          |balm                          |21.0.55             |Manifest: NOSIGNATURE
		baubley-heart-canisters-1.21.1-1.2.3.jar          |Baubley Heart Canisters       |bhc                           |1.21.1-1.2.3        |Manifest: NOSIGNATURE
		BetterAdvancements-NeoForge-1.21.1-0.4.3.21.jar   |Better Advancements           |betteradvancements            |0.4.3.21            |Manifest: NOSIGNATURE
		betterchunkloading-1.21-5.4.jar                   |betterchunkloading mod        |betterchunkloading            |5.4                 |Manifest: NOSIGNATURE
		BiomesOPlenty-neoforge-1.21.1-21.1.0.13.jar       |Biomes O' Plenty              |biomesoplenty                 |21.1.0.13           |Manifest: NOSIGNATURE
		blueflame-1.21.1-1.1.1.jar                        |Blue Flame Burning            |blueflame                     |1.21.1-1.1.1        |Manifest: NOSIGNATURE
		bookshelf-neoforge-1.21.1-21.1.78.jar             |Bookshelf                     |bookshelf                     |21.1.78             |Manifest: NOSIGNATURE
		bowinfinityfix-1.21-neo-3.1.1.jar                 |Bow Infinity Fix              |bowinfinityfix                |3.1.1               |Manifest: NOSIGNATURE
		BrandonsCore-1.21.1-3.2.1.309.jar                 |Brandon's Core                |brandonscore                  |3.2.1.309           |Manifest: 53:bb:a0:11:bd:61:e2:1a:e2:cb:fd:f8:4f:e4:cd:a5:cc:12:f4:43:f0:78:68:3b:e1:62:c6:78:3b:27:ff:fe
		brutalbosses-1.21-8.4.jar                         |brutalbosses mod              |brutalbosses                  |8.4                 |Manifest: NOSIGNATURE
		buildinggadgets2-1.3.9.jar                        |Building Gadgets 2            |buildinggadgets2              |1.3.9               |Manifest: NOSIGNATURE
		BuildingWands-neoforge-MC1.21-2.9.jar             |Building Wands                |wands                         |2.9                 |Manifest: NOSIGNATURE
		caelus-neoforge-7.0.1+1.21.1.jar                  |Caelus API                    |caelus                        |7.0.1+1.21.1        |Manifest: NOSIGNATURE
		charginggadgets-1.14.1.jar                        |Charging Gadgets              |charginggadgets               |1.14.1              |Manifest: NOSIGNATURE
		chisel-neoforge-2.0.0+mc1.21.1.jar                |Chisel Reborn                 |chisel                        |2.0.0+mc1.21.1      |Manifest: NOSIGNATURE
		chisels-and-bits-neoforge-21.1.25.jar             |chisels-and-bits              |chiselsandbits                |21.1.25             |Manifest: NOSIGNATURE
		chloride-NEOFORGE-mc1.21.1-v1.7.3.jar             |Chloride                      |chloride                      |1.7.3               |Manifest: NOSIGNATURE
		chunkactivitytracker-neoforge-1.0.1-1.21.1.jar    |Chunk Activity Tracker        |chunkactivitytracker          |1.0.1               |Manifest: NOSIGNATURE
		cleanswing-1.9.jar                                |Clean Swing                   |cleanswing                    |1.9                 |Manifest: NOSIGNATURE
		cloth-config-15.0.140-neoforge.jar                |Cloth Config v15 API          |cloth_config                  |15.0.140            |Manifest: NOSIGNATURE
		Clumps-neoforge-1.21.1-19.0.0.1.jar               |Clumps                        |clumps                        |19.0.0.1            |Manifest: NOSIGNATURE
		CodeChickenLib-1.21.1-4.6.1.526.jar               |CodeChicken Lib               |codechickenlib                |4.6.1.526           |Manifest: 31:e6:db:63:47:4a:6e:e0:0a:2c:11:d1:76:db:4e:82:ff:56:2d:29:93:d2:e5:02:bd:d3:bd:9d:27:47:a5:71
		Cognition-v2.4.9-1.21.1.jar                       |Cognition                     |cognition                     |2.4.9               |Manifest: NOSIGNATURE
		collective-1.21.1-8.13.jar                        |Collective                    |collective                    |8.13                |Manifest: NOSIGNATURE
		colorfulhearts-neoforge-1.21.1-10.5.9.jar         |Colorful Hearts               |colorfulhearts                |10.5.9              |Manifest: NOSIGNATURE
		comforts-neoforge-9.0.4+1.21.1.jar                |Comforts                      |comforts                      |9.0.4+1.21.1        |Manifest: NOSIGNATURE
		common-networking-neoforge-1.0.21-1.21.1.jar      |Common Networking             |commonnetworking              |1.0.21-1.21.1       |Manifest: NOSIGNATURE
		commoncapabilities-1.21.1-neoforge-2.11.2-296.jar |CommonCapabilities            |commoncapabilities            |2.11.2              |Manifest: NOSIGNATURE
		compactmachines-neoforge-7.0.68.jar               |Compact Machines              |compactmachines               |7.0.68              |Manifest: NOSIGNATURE
		conditional-mixin-neoforge-0.6.4.jar              |conditional mixin             |conditional_mixin             |0.6.4               |Manifest: NOSIGNATURE
		configurable-3.3.0+1.21.1-neoforge.jar            |Configurable                  |configurable                  |3.3.0               |Manifest: NOSIGNATURE
		configured-neoforge-1.21.1-2.6.3.jar              |Configured                    |configured                    |2.6.3               |Manifest: 0d:78:5f:44:c0:47:0c:8c:e2:63:a3:04:43:d4:12:7d:b0:7c:35:37:dc:40:b1:c1:98:ec:51:eb:3b:3c:45:99
		connectedglass-1.1.14-neoforge-mc1.21.jar         |Connected Glass               |connectedglass                |1.1.14              |Manifest: NOSIGNATURE
		connectivity-1.21.1-7.2.jar                       |Connectivity Mod              |connectivity                  |7.2                 |Manifest: NOSIGNATURE
		Controlling-neoforge-1.21.1-19.0.5.jar            |Controlling                   |controlling                   |19.0.5              |Manifest: NOSIGNATURE
		cookingforblockheads-neoforge-1.21.1-21.1.17.jar  |Cooking for Blockheads        |cookingforblockheads          |21.1.17             |Manifest: NOSIGNATURE
		Corgilib-NeoForge-1.21.1-5.0.0.7.jar              |CorgiLib                      |corgilib                      |5.0.0.7             |Manifest: NOSIGNATURE
		cosmeticarmorreworked-1.21.1-v1-neoforge.jar      |CosmeticArmorReworked         |cosmeticarmorreworked         |1.21.1-v1-neoforge  |Manifest: 5e:ed:25:99:e4:44:14:c0:dd:89:c1:a9:4c:10:b5:0d:e4:b1:52:50:45:82:13:d8:d0:32:89:67:56:57:01:53
		crafting_on_a_stick-1.21.0.2.jar                  |Crafting On A Stick           |crafting_on_a_stick           |1.21.0.2            |Manifest: NOSIGNATURE
		craftingtweaks-neoforge-1.21.1-21.1.6.jar         |Crafting Tweaks               |craftingtweaks                |21.1.6              |Manifest: NOSIGNATURE
		CraterLib-Neoforge-1.21-3.0.1.jar                 |CraterLib                     |craterlib                     |3.0.1               |Manifest: NOSIGNATURE
		create-1.21.1-6.0.8.jar                           |Create                        |create                        |6.0.8               |Manifest: NOSIGNATURE
		cristellib-neoforge-1.21.1-3.0.2.1.jar            |Cristel Lib                   |cristellib                    |3.0.2.1             |Manifest: NOSIGNATURE
		cryonicconfig-neoforge-1.0.0+mc1.21.10.jar        |Cryonic Config                |cryonicconfig                 |1.0.0+mc1.21.10     |Manifest: NOSIGNATURE
		Cucumber-1.21.1-8.0.15.jar                        |Cucumber Library              |cucumber                      |8.0.15              |Manifest: NOSIGNATURE
		cumulus_menus-1.21.1-2.0.7-neoforge.jar           |Cumulus                       |cumulus_menus                 |2.0.7               |Manifest: NOSIGNATURE
		cupboard-1.21-2.9.jar                             |Cupboard mod                  |cupboard                      |2.9                 |Manifest: NOSIGNATURE
		curios-neoforge-9.5.1+1.21.1.jar                  |Curios API                    |curios                        |9.5.1+1.21.1        |Manifest: NOSIGNATURE
		cyclopscore-1.21.1-neoforge-1.27.2-848.jar        |Cyclops Core                  |cyclopscore                   |1.27.2              |Manifest: NOSIGNATURE
		deep_aether-1.21.1-1.1.4.jar                      |Deep Aether                   |deep_aether                   |1.1.4               |Manifest: NOSIGNATURE
		Ding-1.21-NeoForge-1.5.0.jar                      |Ding                          |ding                          |1.5.0               |Manifest: ae:67:c5:55:fb:7e:f3:4e:5c:71:f4:50:9e:df:a2:b0:32:86:cf:09:f2:fe:9b:db:94:3b:09:88:a2:3d:91:1f
		does_it_tick-neoforge-1.1.4-1.21.1.jar            |Does It Tick?                 |does_it_tick                  |1.1.4               |Manifest: NOSIGNATURE
		doubledoors-1.21.1-7.2.jar                        |Double Doors                  |doubledoors                   |7.2                 |Manifest: NOSIGNATURE
		Draconic-Evolution-1.21.1-3.1.4.630.jar           |Draconic Evolution            |draconicevolution             |3.1.4.630           |Manifest: 53:bb:a0:11:bd:61:e2:1a:e2:cb:fd:f8:4f:e4:cd:a5:cc:12:f4:43:f0:78:68:3b:e1:62:c6:78:3b:27:ff:fe
		DungeonCrawl-NeoForge-1.21-2.3.15.jar             |Dungeon Crawl                 |dungeoncrawl                  |2.3.15              |Manifest: NOSIGNATURE
		durabilitytooltip-1.1.6-neoforge-mc1.21.jar       |Durability Tooltip            |durabilitytooltip             |1.1.6               |Manifest: NOSIGNATURE
		EdivadLib-1.21-3.0.0.jar                          |EdivadLib                     |edivadlib                     |3.0.0               |Manifest: NOSIGNATURE
		elevatorid-neoforge-1.21.1-1.11.4.jar             |ElevatorMod                   |elevatorid                    |1.21.1-1.11.4       |Manifest: NOSIGNATURE
		enchdesc-neoforge-1.21.1-21.1.9.jar               |EnchantmentDescriptions       |enchdesc                      |21.1.9              |Manifest: NOSIGNATURE
		com.enderio.endercore-8.0.7-alpha.jar             |Ender Core                    |endercore                     |8.0.7-alpha         |Manifest: NOSIGNATURE
		enderio-8.0.7-alpha.jar                           |Ender IO                      |enderio                       |8.0.7-alpha         |Manifest: NOSIGNATURE
		com.enderio.enderio-armory-8.0.7-alpha.jar        |Ender IO Armory               |enderio_armory                |8.0.7-alpha         |Manifest: NOSIGNATURE
		com.enderio.enderio-base-8.0.7-alpha.jar          |Ender IO Base                 |enderio_base                  |8.0.7-alpha         |Manifest: NOSIGNATURE
		com.enderio.enderio-conduits-8.0.7-alpha.jar      |Ender IO Conduits             |enderio_conduits              |8.0.7-alpha         |Manifest: NOSIGNATURE
		com.enderio.enderio-machines-8.0.7-alpha.jar      |Ender IO Machines             |enderio_machines              |8.0.7-alpha         |Manifest: NOSIGNATURE
		com.enderio.enderio-conduits-modded-8.0.7-alpha.ja|Ender IO Modded Conduits      |enderio_conduits_modded       |8.0.7-alpha         |Manifest: NOSIGNATURE
		EnderStorage-1.21.1-2.13.0.191.jar                |EnderStorage                  |enderstorage                  |2.13.0.191          |Manifest: 31:e6:db:63:47:4a:6e:e0:0a:2c:11:d1:76:db:4e:82:ff:56:2d:29:93:d2:e5:02:bd:d3:bd:9d:27:47:a5:71
		aether_enhanced_extinguishing-1.21.1-1.0.0-neoforg|Enhanced Extinguishing        |aether_enhanced_extinguishing |1.0.0               |Manifest: NOSIGNATURE
		entangled-1.3.20a-neoforge-mc1.21.jar             |Entangled                     |entangled                     |1.3.20+a            |Manifest: NOSIGNATURE
		entity_model_features_1.21-neoforge-3.0.7.jar     |Entity Model Features         |entity_model_features         |3.0.7               |Manifest: NOSIGNATURE
		entity_texture_features_1.21-neoforge-7.0.6.jar   |Entity Texture Features       |entity_texture_features       |7.0.6               |Manifest: NOSIGNATURE
		entityculling-neoforge-1.9.3-mc1.21.1.jar         |EntityCulling                 |entityculling                 |1.9.3               |Manifest: NOSIGNATURE
		everlastingabilities-1.21.1-neoforge-2.5.4-300.jar|EverlastingAbilities          |everlastingabilities          |2.5.4               |Manifest: NOSIGNATURE
		expandability-neoforge-12.0.0.jar                 |ExpandAbility                 |expandability                 |12.0.0              |Manifest: NOSIGNATURE
		explore_ruins_aether-1.0.0-neoforge-1.21.1.jar    |Explore Ruins Aether          |explore_ruins_aether          |1.0.0               |Manifest: NOSIGNATURE
		Explorify v1.6.4 f15-88.mod.jar                   |Explorify                     |explorify                     |1.6.4               |Manifest: NOSIGNATURE
		ExtendedAE-1.21-2.2.26-neoforge.jar               |ExtendedAE                    |extendedae                    |1.21-2.2.26-neoforge|Manifest: NOSIGNATURE
		ExtraDisks-1.21.1-4.0.14.jar                      |Extra Disks                   |extradisks                    |1.21.1-4.0.14       |Manifest: NOSIGNATURE
		ExtraStorage-1.21.1-5.0.7.jar                     |ExtraStorage                  |extrastorage                  |5.0.7               |Manifest: NOSIGNATURE
		ExtremeReactors2-1.21.1-2.4.27.jar                |Extreme Reactors              |bigreactors                   |1.21.1-2.4.27       |Manifest: NOSIGNATURE
		ExtremeSoundMuffler-3.51_NeoForge-1.21.jar        |Extreme Sound Muffler         |extremesoundmuffler           |3.51                |Manifest: NOSIGNATURE
		fallingleaves-1.21.1-2.5.1.jar                    |Fallingleaves                 |fallingleaves                 |2.5.1               |Manifest: NOSIGNATURE
		FarmersDelight-1.21.1-1.2.9.jar                   |Farmer's Delight              |farmersdelight                |1.2.9               |Manifest: NOSIGNATURE
		farmingforblockheads-neoforge-1.21.1-21.1.10.jar  |Farming for Blockheads        |farmingforblockheads          |21.1.10             |Manifest: NOSIGNATURE
		fast-ip-ping-v1.0.7-mc1.21.1-neoforge.jar         |Fast IP Ping                  |fastipping                    |1.0.7               |Manifest: NOSIGNATURE
		FastItemFrames-v21.1.6-1.21.1-NeoForge.jar        |Fast Item Frames              |fastitemframes                |21.1.6              |Manifest: NOSIGNATURE
		fastpaintings-1.21-1.3.0-neoforge.jar             |Fast Paintings                |fastpaintings                 |1.21-1.3.0          |Manifest: NOSIGNATURE
		FastSuite-1.21.1-6.0.5.jar                        |Fast Suite                    |fastsuite                     |6.0.5               |Manifest: NOSIGNATURE
		fastasyncworldsave-1.21-2.6.jar                   |fastasyncworldsave mod        |fastasyncworldsave            |2.6                 |Manifest: NOSIGNATURE
		fastleafdecay-35.jar                              |FastLeafDecay                 |fastleafdecay                 |35                  |Manifest: NOSIGNATURE
		ferritecore-7.0.2-neoforge.jar                    |Ferrite Core                  |ferritecore                   |7.0.2               |Manifest: 41:ce:50:66:d1:a0:05:ce:a1:0e:02:85:9b:46:64:e0:bf:2e:cf:60:30:9a:fe:0c:27:e0:63:66:9a:84:ce:8a
		flerovium-neoforge-1.21.1-1.0.15-all.jar          |Flerovium                     |flerovium                     |1.0.15              |Manifest: NOSIGNATURE
		FluxNetworks-1.21.1-8.0.0.jar                     |Flux Networks                 |fluxnetworks                  |8.0.0               |Manifest: NOSIGNATURE
		flywheel-neoforge-1.21.1-1.0.5.jar                |Flywheel                      |flywheel                      |1.0.5               |Manifest: NOSIGNATURE
		ForgeEndertech-1.21.1-12.1.1.0-NeoForge-build.0471|ForgeEndertech                |forgeendertech                |12.1.1.0            |Manifest: NOSIGNATURE
		forgified-fabric-api-0.115.6+2.1.0+1.21.1.jar     |Forgified Fabric API          |fabric_api                    |0.115.6+2.1.0+1.21.1|Manifest: NOSIGNATURE
		fabric-api-base-0.4.42+d1308dedd1.jar             |Forgified Fabric API Base     |fabric_api_base               |0.4.42+d1308dedd1   |Manifest: NOSIGNATURE
		fabric-api-lookup-api-v1-1.6.70+c21168c319.jar    |Forgified Fabric API Lookup AP|fabric_api_lookup_api_v1      |1.6.70+c21168c319   |Manifest: NOSIGNATURE
		fabric-biome-api-v1-13.0.31+1e62d33c19.jar        |Forgified Fabric Biome API (v1|fabric_biome_api_v1           |13.0.31+1e62d33c19  |Manifest: NOSIGNATURE
		fabric-block-api-v1-1.0.22+a6e994cd19.jar         |Forgified Fabric Block API (v1|fabric_block_api_v1           |1.0.22+a6e994cd19   |Manifest: NOSIGNATURE
		fabric-blockrenderlayer-v1-1.1.52+b089b4bd19.jar  |Forgified Fabric BlockRenderLa|fabric_blockrenderlayer_v1    |1.1.52+b089b4bd19   |Manifest: NOSIGNATURE
		fabric-block-view-api-v2-1.0.11+e9036fd419.jar    |Forgified Fabric BlockView API|fabric_block_view_api_v2      |1.0.11+e9036fd419   |Manifest: NOSIGNATURE
		fabric-client-tags-api-v1-1.1.15+e053909619.jar   |Forgified Fabric Client Tags  |fabric_client_tags_api_v1     |1.1.15+e053909619   |Manifest: NOSIGNATURE
		fabric-command-api-v2-2.2.28+36d727be19.jar       |Forgified Fabric Command API (|fabric_command_api_v2         |2.2.28+36d727be19   |Manifest: NOSIGNATURE
		fabric-content-registries-v0-8.0.18+0a0c14ff19.jar|Forgified Fabric Content Regis|fabric_content_registries_v0  |8.0.18+0a0c14ff19   |Manifest: NOSIGNATURE
		fabric-convention-tags-v1-2.1.4+7f945d5b19.jar    |Forgified Fabric Convention Ta|fabric_convention_tags_v1     |2.1.4+7f945d5b19    |Manifest: NOSIGNATURE
		fabric-convention-tags-v2-2.11.0+87e5848019.jar   |Forgified Fabric Convention Ta|fabric_convention_tags_v2     |2.11.0+87e5848019   |Manifest: NOSIGNATURE
		fabric-data-attachment-api-v1-1.4.3+58235da019.jar|Forgified Fabric Data Attachme|fabric_data_attachment_api_v1 |1.4.3+58235da019    |Manifest: NOSIGNATURE
		fabric-data-generation-api-v1-20.2.28+2d91a6db19.j|Forgified Fabric Data Generati|fabric_data_generation_api_v1 |20.2.28+2d91a6db19  |Manifest: NOSIGNATURE
		fabric-entity-events-v1-1.7.0+1af6e62419.jar      |Forgified Fabric Entity Events|fabric_entity_events_v1       |1.7.0+1af6e62419    |Manifest: NOSIGNATURE
		fabric-events-interaction-v0-0.7.13+7b71cc1619.jar|Forgified Fabric Events Intera|fabric_events_interaction_v0  |0.7.13+7b71cc1619   |Manifest: NOSIGNATURE
		fabric-game-rule-api-v1-1.0.53+36d727be19.jar     |Forgified Fabric Game Rule API|fabric_game_rule_api_v1       |1.0.53+36d727be19   |Manifest: NOSIGNATURE
		fabric-gametest-api-v1-2.0.5+29f188ce19.jar       |Forgified Fabric Game Test API|fabric_gametest_api_v1        |2.0.5+29f188ce19    |Manifest: NOSIGNATURE
		fabric-item-api-v1-11.1.1+57cdfa8219.jar          |Forgified Fabric Item API (v1)|fabric_item_api_v1            |11.1.1+57cdfa8219   |Manifest: NOSIGNATURE
		fabric-item-group-api-v1-4.1.7+e324903319.jar     |Forgified Fabric Item Group AP|fabric_item_group_api_v1      |4.1.7+e324903319    |Manifest: NOSIGNATURE
		fabric-key-binding-api-v1-1.0.47+62cc7ce119.jar   |Forgified Fabric Key Binding A|fabric_key_binding_api_v1     |1.0.47+62cc7ce119   |Manifest: NOSIGNATURE
		fabric-lifecycle-events-v1-2.5.0+a2ee258a19.jar   |Forgified Fabric Lifecycle Eve|fabric_lifecycle_events_v1    |2.5.0+a2ee258a19    |Manifest: NOSIGNATURE
		fabric-loot-api-v2-3.0.15+a3ee712d19.jar          |Forgified Fabric Loot API (v2)|fabric_loot_api_v2            |3.0.15+a3ee712d19   |Manifest: NOSIGNATURE
		fabric-loot-api-v3-1.0.3+333dfad919.jar           |Forgified Fabric Loot API (v3)|fabric_loot_api_v3            |1.0.3+333dfad919    |Manifest: NOSIGNATURE
		fabric-message-api-v1-6.0.13+e053909619.jar       |Forgified Fabric Message API (|fabric_message_api_v1         |6.0.13+e053909619   |Manifest: NOSIGNATURE
		fabric-model-loading-api-v1-2.0.0+986ae77219.jar  |Forgified Fabric Model Loading|fabric_model_loading_api_v1   |2.0.0+986ae77219    |Manifest: NOSIGNATURE
		fabric-networking-api-v1-4.3.0+4f690eb619.jar     |Forgified Fabric Networking AP|fabric_networking_api_v1      |4.3.0+4f690eb619    |Manifest: NOSIGNATURE
		fabric-object-builder-api-v1-15.2.1+cc242efd19.jar|Forgified Fabric Object Builde|fabric_object_builder_api_v1  |15.2.1+cc242efd19   |Manifest: NOSIGNATURE
		fabric-particles-v1-4.0.2+824f924c19.jar          |Forgified Fabric Particles (v1|fabric_particles_v1           |4.0.2+824f924c19    |Manifest: NOSIGNATURE
		fabric-recipe-api-v1-5.0.14+59440bcc19.jar        |Forgified Fabric Recipe API (v|fabric_recipe_api_v1          |5.0.14+59440bcc19   |Manifest: NOSIGNATURE
		fabric-registry-sync-v0-5.2.0+867470b919.jar      |Forgified Fabric Registry Sync|fabric_registry_sync_v0       |5.2.0+867470b919    |Manifest: NOSIGNATURE
		fabric-renderer-indigo-1.7.0+4198af7119.jar       |Forgified Fabric Renderer - In|fabric_renderer_indigo        |1.7.0+4198af7119    |Manifest: NOSIGNATURE
		fabric-renderer-api-v1-3.4.0+acb05a3919.jar       |Forgified Fabric Renderer API |fabric_renderer_api_v1        |3.4.0+acb05a3919    |Manifest: NOSIGNATURE
		fabric-rendering-v1-5.0.5+077ba95f19.jar          |Forgified Fabric Rendering (v1|fabric_rendering_v1           |5.0.5+077ba95f19    |Manifest: NOSIGNATURE
		fabric-rendering-data-attachment-v1-0.3.49+73761d2|Forgified Fabric Rendering Dat|fabric_rendering_data_attachme|0.3.49+73761d2e19   |Manifest: NOSIGNATURE
		fabric-rendering-fluids-v1-3.1.6+857185bc19.jar   |Forgified Fabric Rendering Flu|fabric_rendering_fluids_v1    |3.1.6+857185bc19    |Manifest: NOSIGNATURE
		fabric-resource-conditions-api-v1-4.3.0+5bdd099819|Forgified Fabric Resource Cond|fabric_resource_conditions_api|4.3.0+5bdd099819    |Manifest: NOSIGNATURE
		fabric-resource-loader-v0-1.3.1+4ea8954419.jar    |Forgified Fabric Resource Load|fabric_resource_loader_v0     |1.3.1+4ea8954419    |Manifest: NOSIGNATURE
		fabric-screen-api-v1-2.0.25+4228281319.jar        |Forgified Fabric Screen API (v|fabric_screen_api_v1          |2.0.25+4228281319   |Manifest: NOSIGNATURE
		fabric-screen-handler-api-v1-1.3.88+8dbc56dd19.jar|Forgified Fabric Screen Handle|fabric_screen_handler_api_v1  |1.3.88+8dbc56dd19   |Manifest: NOSIGNATURE
		fabric-sound-api-v1-1.0.23+10b84f8419.jar         |Forgified Fabric Sound API (v1|fabric_sound_api_v1           |1.0.23+10b84f8419   |Manifest: NOSIGNATURE
		fabric-transfer-api-v1-5.4.2+a25cb45619.jar       |Forgified Fabric Transfer API |fabric_transfer_api_v1        |5.4.2+a25cb45619    |Manifest: NOSIGNATURE
		fabric-transitive-access-wideners-v1-6.2.0+6c854b6|Forgified Fabric Transitive Ac|fabric_transitive_access_widen|6.2.0+6c854b6f19    |Manifest: NOSIGNATURE
		forgivingvoid-neoforge-1.21.1-21.1.5.jar          |Forgiving Void                |forgivingvoid                 |21.1.5              |Manifest: NOSIGNATURE
		FramedBlocks-10.5.1.jar                           |FramedBlocks                  |framedblocks                  |10.5.1              |Manifest: NOSIGNATURE
		framework-neoforge-1.21.1-0.13.5.jar              |Framework                     |framework                     |0.13.5              |Manifest: NOSIGNATURE
		ftbbackups2-neoforge-1.21-1.0.28.jar              |FTB Backups 2                 |ftbbackups2                   |1.0.28              |Manifest: NOSIGNATURE
		ftb-chunks-neoforge-2101.1.13.jar                 |FTB Chunks                    |ftbchunks                     |2101.1.13           |Manifest: NOSIGNATURE
		ftb-library-neoforge-2101.1.28.jar                |FTB Library                   |ftblibrary                    |2101.1.28           |Manifest: NOSIGNATURE
		ftb-quests-neoforge-2101.1.19.jar                 |FTB Quests                    |ftbquests                     |2101.1.19           |Manifest: NOSIGNATURE
		ftb-teams-neoforge-2101.1.7.jar                   |FTB Teams                     |ftbteams                      |2101.1.7            |Manifest: NOSIGNATURE
		functionalstorage-1.21.1-1.5.5.jar                |Functional Storage            |functionalstorage             |1.21.1-1.5.5        |Manifest: NOSIGNATURE
		fusion-1.2.11b-neoforge-mc1.21.jar                |Fusion                        |fusion                        |1.2.11+b            |Manifest: NOSIGNATURE
		fzzy_config-0.7.3+1.21+neoforge.jar               |Fzzy Config                   |fzzy_config                   |0.7.3+1.21+neoforge |Manifest: NOSIGNATURE
		geckolib-neoforge-1.21.1-4.8.2.jar                |GeckoLib 4                    |geckolib                      |4.8.2               |Manifest: NOSIGNATURE
		GlitchCore-neoforge-1.21.1-2.1.0.0.jar            |GlitchCore                    |glitchcore                    |2.1.0.0             |Manifest: NOSIGNATURE
		Glodium-1.21-2.2-neoforge.jar                     |Glodium                       |glodium                       |1.21-2.2-neoforge   |Manifest: NOSIGNATURE
		gpumemleakfix-1.21-1.8.jar                        |Gpu memory leak fix           |gpumemleakfix                 |1.8                 |Manifest: NOSIGNATURE
		gravestone-neoforge-1.21.1-1.0.35.jar             |Gravestone Mod                |gravestone                    |1.21.1-1.0.35       |Manifest: NOSIGNATURE
		guideme-21.1.15.jar                               |GuideME                       |guideme                       |21.1.15             |Manifest: NOSIGNATURE
		Icarus-NeoForge-4.6.3.jar                         |Icarus                        |icarus                        |4.6.3               |Manifest: NOSIGNATURE
		iChunUtil-1.21-NeoForge-1.0.3.jar                 |iChunUtil                     |ichunutil                     |1.0.3               |Manifest: ae:67:c5:55:fb:7e:f3:4e:5c:71:f4:50:9e:df:a2:b0:32:86:cf:09:f2:fe:9b:db:94:3b:09:88:a2:3d:91:1f
		ImmediatelyFast-NeoForge-1.6.7+1.21.1.jar         |ImmediatelyFast               |immediatelyfast               |1.6.7+1.21.1        |Manifest: NOSIGNATURE
		ImmersiveEngineering-1.21.1-12.4.2-194.jar        |Immersive Engineering         |immersiveengineering          |12.4.2-194          |Manifest: NOSIGNATURE
		immersive_paintings-neoforge-1.21.1-0.7.4.jar     |Immersive Paintings           |immersive_paintings           |0.7.4               |Manifest: NOSIGNATURE
		Incendium_1.21.x_v5.4.4.jar                       |Incendium                     |incendium                     |5.4.3               |Manifest: NOSIGNATURE
		industrialforegoing-1.21-3.6.36.jar               |Industrial Foregoing          |industrialforegoing           |1.21-3.6.36         |Manifest: NOSIGNATURE
		infernalmobs-1.21.1.3NF.jar                       |Infernal Mobs                 |infernalmobs                  |1.21.1.3NF          |Manifest: NOSIGNATURE
		integratedcrafting-1.21.1-neoforge-1.3.4.jar      |IntegratedCrafting            |integratedcrafting            |1.3.4               |Manifest: NOSIGNATURE
		integrateddynamics-1.21.1-neoforge-1.29.6.jar     |IntegratedDynamics            |integrateddynamics            |1.29.6              |Manifest: NOSIGNATURE
		integratedterminals-1.21.1-neoforge-1.6.21-649.jar|IntegratedTerminals           |integratedterminals           |1.6.21              |Manifest: NOSIGNATURE
		integratedtunnels-1.21.1-neoforge-1.9.2-521.jar   |IntegratedTunnels             |integratedtunnels             |1.9.2               |Manifest: NOSIGNATURE
		inventoryhud.neoforged.1.21.1-3.4.28.jar          |Inventory HUD+                |inventoryhud                  |3.4.28              |Manifest: NOSIGNATURE
		ironchest-1.21-neoforge-16.0.7.jar                |Iron Chests                   |ironchest                     |1.21-neoforge-16.0.7|Manifest: NOSIGNATURE
		ironfurnaces-neoforge-1.21.1-4.3.2.jar            |Iron Furnaces                 |ironfurnaces                  |4.3.2               |Manifest: NOSIGNATURE
		IronJetpacks-1.21.1-8.0.11.jar                    |Iron Jetpacks                 |ironjetpacks                  |8.0.11              |Manifest: NOSIGNATURE
		irons_spellbooks-1.21.1-3.14.8.jar                |Iron's Spells 'n Spellbooks   |irons_spellbooks              |1.21.1-3.14.8       |Manifest: NOSIGNATURE
		itemcollectors-1.1.10-neoforge-mc1.21.jar         |Item Collectors               |itemcollectors                |1.1.10              |Manifest: NOSIGNATURE
		Jade-1.21.1-NeoForge-15.10.3.jar                  |Jade                          |jade                          |15.10.3+neoforge    |Manifest: NOSIGNATURE
		JadeAddons-1.21.1-NeoForge-6.1.0.jar              |Jade Addons                   |jadeaddons                    |6.1.0+neoforge      |Manifest: NOSIGNATURE
		jamlib-neoforge-1.3.5+1.21.1.jar                  |JamLib                        |jamlib                        |1.3.5+1.21.1        |Manifest: NOSIGNATURE
		journeymap-neoforge-1.21.1-6.0.0-beta.52.jar      |Journeymap                    |journeymap                    |1.21.1-6.0.0-beta.52|Manifest: NOSIGNATURE
		journeymap-api-neoforge-2.0.0-1.21.1-SNAPSHOT.jar |JourneyMap API                |journeymap_api                |2.0.0               |Manifest: NOSIGNATURE
		jei-1.21.1-neoforge-19.25.1.332.jar               |Just Enough Items             |jei                           |19.25.1.332         |Manifest: NOSIGNATURE
		JustEnoughMekanismMultiblocks-1.21.1-7.11.jar     |Just Enough Mekanism Multibloc|jei_mekanism_multiblocks      |7.11                |Manifest: NOSIGNATURE
		JustEnoughResources-NeoForge-1.21.1-1.6.0.17.jar  |Just Enough Resources         |jeresources                   |1.6.0.17            |Manifest: NOSIGNATURE
		keybindspurger-1.21.x-neoforge-1.3.4.jar          |KeybindsPurger                |keybindspurger                |1.3.4               |Manifest: NOSIGNATURE
		thedarkcolour.kffmod-5.10.0.jar                   |Kotlin For Forge              |kotlinforforge                |5.10.0              |Manifest: NOSIGNATURE
		kuma-api-neoforge-21.0.7+1.21.jar                 |KumaAPI                       |kuma_api                      |21.0.7              |Manifest: NOSIGNATURE
		lambdynamiclights-api-4.5.1+1.21.1-mojmap.jar     |LambDynamicLights (API)       |lambdynlights_api             |4.5.1+1.21.1        |Manifest: NOSIGNATURE
		AdLods-1.21.1-9.1.2.0-NeoForge-build.0619.jar     |Large Ore Deposits            |adlods                        |9.1.2.0             |Manifest: NOSIGNATURE
		lithium-neoforge-0.15.1+mc1.21.1.jar              |Lithium                       |lithium                       |0.15.1+mc1.21.1     |Manifest: NOSIGNATURE
		lmft-1.1.1+1.21.9-neoforge.jar                    |Load My F***ing Tags          |lmft                          |1.1.1+1.21.9        |Manifest: NOSIGNATURE
		lootr-neoforge-1.21-1.10.35.96.jar                |Lootr                         |lootr                         |1.21-1.10.35.96     |Manifest: NOSIGNATURE
		mcw-mcwwindows-2.4.1-mc1.21.1neoforge.jar         |Macaw's Windows               |mcwwindows                    |2.4.1               |Manifest: NOSIGNATURE
		maxhealthfix-neoforge-1.21.1-21.1.4.jar           |MaxHealthFix                  |maxhealthfix                  |21.1.4              |Manifest: NOSIGNATURE
		mcjtylib-1.21-9.0.20.jar                          |McJtyLib                      |mcjtylib                      |1.21-9.0.20         |Manifest: NOSIGNATURE
		merequester-neoforge-1.21.1-1.4.1.jar             |ME Requester                  |merequester                   |1.21.1-1.4.1        |Manifest: NOSIGNATURE
		Measurements-neoforge-1.21.1-3.0.3.jar            |Measurements                  |measurements                  |3.0.3               |Manifest: NOSIGNATURE
		megacells-4.10.1.jar                              |MEGA Cells                    |megacells                     |4.10.1              |Manifest: NOSIGNATURE
		Mekanism-1.21.1-10.7.17.83.jar                    |Mekanism                      |mekanism                      |10.7.17             |Manifest: NOSIGNATURE
		MekanismGenerators-1.21.1-10.7.17.83.jar          |Mekanism: Generators          |mekanismgenerators            |10.7.17             |Manifest: NOSIGNATURE
		MekanismTools-1.21.1-10.7.17.83.jar               |Mekanism: Tools               |mekanismtools                 |10.7.17             |Manifest: NOSIGNATURE
		memorysettings-1.21-5.9.jar                       |memorysettings mod            |memorysettings                |5.9                 |Manifest: NOSIGNATURE
		client-1.21.1-20240808.144430-srg.jar             |Minecraft                     |minecraft                     |1.21.1              |Manifest: a1:d4:5e:04:4f:d3:d6:e0:7b:37:97:cf:77:b0:de:ad:4a:47:ce:8c:96:49:5f:0a:cf:8c:ae:b2:6d:4b:8a:3f
		dummmmmmy-1.21-2.0.11-neoforge.jar                |MmmMmmMmmMmm                  |dummmmmmy                     |1.21-2.0.11         |Manifest: NOSIGNATURE
		mob_grinding_utils-1.1.10+mc1.21.1.jar            |Mob Grinding Utils            |mob_grinding_utils            |1.1.10+mc1.21.1     |Manifest: NOSIGNATURE
		modnametooltip-1.21.1-neoforge-2.3.0.jar          |Mod Name Tooltip              |modnametooltip                |2.3.0               |Manifest: NOSIGNATURE
		modelfix-1.21-1.10.jar                            |Model Gap Fix                 |modelfix                      |1.21-1.10           |Manifest: NOSIGNATURE
		modernfix-neoforge-5.25.1+mc1.21.1.jar            |ModernFix                     |modernfix                     |5.25.1+mc1.21.1     |Manifest: NOSIGNATURE
		modonomicon-1.21.1-neoforge-1.117.2.jar           |Modonomicon                   |modonomicon                   |1.117.2             |Manifest: NOSIGNATURE
		mffs-5.4.25.jar                                   |Modular Force Field System    |mffs                          |5.4.25              |Manifest: NOSIGNATURE
		modular-routers-13.2.3+mc1.21.1.jar               |Modular Routers               |modularrouters                |13.2.3              |Manifest: NOSIGNATURE
		moonlight-1.21-2.27.1-neoforge.jar                |Moonlight Lib                 |moonlight                     |1.21-2.27.1         |Manifest: NOSIGNATURE
		moreoverlays-1.24.2-mc1.21.1-neoforge.jar         |More Overlays Updated         |moreoverlays                  |1.24.2              |Manifest: NOSIGNATURE
		MouseTweaks-neoforge-mc1.21-2.26.1.jar            |Mouse Tweaks                  |mousetweaks                   |2.26.1              |Manifest: NOSIGNATURE
		mowziesmobs-1.21.1-1.7.5.jar                      |Mowzie's Mobs                 |mowziesmobs                   |1.7.5               |Manifest: NOSIGNATURE
		MysticalAgradditions-1.21.1-8.0.11.jar            |Mystical Agradditions         |mysticalagradditions          |8.0.11              |Manifest: NOSIGNATURE
		MysticalAgriculture-1.21.1-8.0.21.jar             |Mystical Agriculture          |mysticalagriculture           |8.0.21              |Manifest: NOSIGNATURE
		NaNny-1.21.1-1.0.1.jar                            |NaNny                         |nanny                         |1.0.1               |Manifest: NOSIGNATURE
		NaturesCompass-1.21.1-3.0.3-neoforge.jar          |Nature's Compass              |naturescompass                |1.21.1-3.0.2-neoforg|Manifest: NOSIGNATURE
		Neat-1.21-40-NEOFORGE.jar                         |Neat                          |neat                          |1.21-40-NEOFORGE    |Manifest: NOSIGNATURE
		neoforge-21.1.216-universal.jar                   |NeoForge                      |neoforge                      |21.1.216            |Manifest: NOSIGNATURE
		netherportalfix-neoforge-1.21.1-21.1.1.jar        |NetherPortalFix               |netherportalfix               |21.1.1              |Manifest: NOSIGNATURE
		nitrogen_internals-1.21.1-1.1.25-neoforge.jar     |Nitrogen                      |nitrogen_internals            |1.1.25              |Manifest: NOSIGNATURE
		NoChatReports-NEOFORGE-1.21.1-v2.9.1.jar          |No Chat Reports               |nochatreports                 |1.21.1-v2.9.1       |Manifest: NOSIGNATURE
		novillagerdm-1.21.1-6.0.0.jar                     |No Villager Death Messages    |novillagerdm                  |6.0.0               |Manifest: NOSIGNATURE
		Not Enough Recipe Book-NEOFORGE-0.4.3+1.21.jar    |Not Enough Recipe Book        |nerb                          |0.4.3               |Manifest: NOSIGNATURE
		notenoughwands-1.21-7.0.3.jar                     |Not Enough Wands              |notenoughwands                |1.21-7.0.3          |Manifest: NOSIGNATURE
		nuggets-neoforge-1.21-1.0.10.41.jar               |Nuggets                       |nuggets                       |1.0.10.41           |Manifest: NOSIGNATURE
		occultism-1.21.1-neoforge-1.197.0.jar             |Occultism                     |occultism                     |1.197.0             |Manifest: NOSIGNATURE
		OctoLib-NEOFORGE-0.6.0.4+1.21.jar                 |OctoLib                       |octolib                       |0.6.0.4             |Manifest: NOSIGNATURE
		Oh-The-Biomes-Weve-Gone-NeoForge-2.5.2.jar        |Oh The Biomes We've Gone      |biomeswevegone                |2.5.2               |Manifest: NOSIGNATURE
		Oh-The-Trees-Youll-Grow-neoforge-1.21.1-5.1.2.jar |Oh The Trees You'll Grow      |ohthetreesyoullgrow           |5.1.2               |Manifest: NOSIGNATURE
		OreExcavation-NeoForge-1.21.1-1.16.43.jar         |OreExcavation                 |oreexcavation                 |1.16.43             |Manifest: c4:30:39:dd:35:16:ee:5a:f1:1e:93:a0:ab:b3:75:7f:09:bd:68:20:da:32:8c:17:52:08:42:ed:9c:bc:e1:cb
		overloadedarmorbar-neoforge-1.21-2.jar            |OverloadedArmorBar            |overloadedarmorbar            |2                   |Manifest: NOSIGNATURE
		owo-lib-neoforge-0.12.15.5-beta.1+1.21.jar        |oωo                           |owo                           |0.12.15.5-beta.1+1.2|Manifest: NOSIGNATURE
		packetfixer-3.3.1-1.20.5-1.21.X-merged.jar        |PacketFixer                   |packetfixer                   |3.3.1               |Manifest: NOSIGNATURE
		pamhc2trees-NEOFORGE-1.21.1-1.0.5.jar             |Pam's HarvestCraft - Trees    |pamhc2trees                   |1.0.5               |Manifest: NOSIGNATURE
		particle_core-0.2.6+1.21+neoforge.jar             |Particle Core                 |particle_core                 |0.2.6+1.21+neoforge |Manifest: NOSIGNATURE
		Patchouli-1.21.1-92-NEOFORGE.jar                  |Patchouli                     |patchouli                     |1.21.1-92-NEOFORGE  |Manifest: NOSIGNATURE
		PickleTweaks-1.21.1-9.0.5.jar                     |Pickle Tweaks                 |pickletweaks                  |9.0.5               |Manifest: NOSIGNATURE
		pipez-neoforge-1.21.1-1.2.19.jar                  |Pipez                         |pipez                         |1.21.1-1.2.19       |Manifest: NOSIGNATURE
		Placebo-1.21.1-9.9.1.jar                          |Placebo                       |placebo                       |9.9.1               |Manifest: NOSIGNATURE
		player-animation-lib-forge-2.0.1+1.21.1.jar       |Player Animator               |playeranimator                |2.0.1+1.21.1        |Manifest: NOSIGNATURE
		pneumaticcraft-repressurized-8.2.14+mc1.21.1.jar  |PneumaticCraft: Repressurized |pneumaticcraft                |8.2.14              |Manifest: NOSIGNATURE
		polylib-2100.1.0-build.183-neoforge.jar           |PolyLib                       |polylib                       |2100.1.0-build.183  |Manifest: NOSIGNATURE
		polymorph-neoforge-1.1.0+1.21.1.jar               |Polymorph                     |polymorph                     |1.1.0+1.21.1        |Manifest: NOSIGNATURE
		polyeng-0.4.1.jar                                 |Polymorphic Energistics       |polyeng                       |0.4.1               |Manifest: NOSIGNATURE
		Ponder-NeoForge-1.21.1-1.0.64.jar                 |Ponder                        |ponder                        |1.0.64              |Manifest: NOSIGNATURE
		Powah-6.2.7.jar                                   |Powah                         |powah                         |6.2.7               |Manifest: NOSIGNATURE
		prickle-neoforge-1.21.1-21.1.11.jar               |PrickleMC                     |prickle                       |21.1.11             |Manifest: NOSIGNATURE
		ProjectE-1.21.1-PE1.1.0.jar                       |ProjectE                      |projecte                      |1.1.0               |Manifest: NOSIGNATURE
		PuzzlesLib-v21.1.39-1.21.1-NeoForge.jar           |Puzzles Lib                   |puzzleslib                    |21.1.39             |Manifest: NOSIGNATURE
		rangedpumps-1.3.0.jar                             |Ranged Pumps                  |rangedpumps                   |1.3.0               |Manifest: NOSIGNATURE
		rechiseled-1.1.6a-neoforge-mc1.21.jar             |Rechiseled                    |rechiseled                    |1.1.6+a             |Manifest: NOSIGNATURE
		recipeessentials-1.21-4.0.jar                     |recipeessentials mod          |recipeessentials              |4.0                 |Manifest: NOSIGNATURE
		redirected-neoforge-1.0.0-1.21.1.jar              |Redirected                    |redirected                    |1.0.0               |Manifest: NOSIGNATURE
		reeses-sodium-options-neoforge-1.8.3+mc1.21.4.jar |Reese's Sodium Options        |reeses_sodium_options         |1.8.3+mc1.21.4      |Manifest: NOSIGNATURE
		refinedstorage-neoforge-2.0.0.jar                 |Refined Storage               |refinedstorage                |2.0.0               |Manifest: NOSIGNATURE
		refinedstorage-jei-integration-neoforge-1.0.0.jar |Refined Storage - JEI Integrat|refinedstorage_jei_integration|1.0.0               |Manifest: NOSIGNATURE
		refinedstorage-mekanism-integration-1.1.1.jar     |Refined Storage - Mekanism Int|refinedstorage_mekanism_integr|1.1.1               |Manifest: NOSIGNATURE
		refinedstorage-quartz-arsenal-neoforge-1.0.6.jar  |Refined Storage - Quartz Arsen|refinedstorage_quartz_arsenal |1.0.6               |Manifest: NOSIGNATURE
		regions_unexplored-neoforge-1.21.1-0.5.6.1.jar    |Regions Unexplored            |regions_unexplored            |0.5.6.1             |Manifest: NOSIGNATURE
		relics-1.21.1-0.11.3.jar                          |Relics                        |relics                        |0.11.3              |Manifest: NOSIGNATURE
		reliquary-1.21.1-2.0.62.1310.jar                  |Reliquary Reincarnations      |reliquary                     |2.0.62              |Manifest: NOSIGNATURE
		rrls-5.0.10+mc1.21.1-forge.jar                    |Remove Reloading Screen       |rrls                          |5.0.10+mc1.21.1-forg|Manifest: NOSIGNATURE
		resourcefulconfig-neoforge-1.21-3.0.11.jar        |Resourcefulconfig             |resourcefulconfig             |3.0.11              |Manifest: NOSIGNATURE
		rftoolsbase-1.21-6.0.10.jar                       |RFToolsBase                   |rftoolsbase                   |1.21-6.0.10         |Manifest: NOSIGNATURE
		rftoolsbuilder-1.21-7.0.4.jar                     |RFToolsBuilder                |rftoolsbuilder                |1.21-7.0.4          |Manifest: NOSIGNATURE
		rftoolscontrol-1.21-8.0.1.jar                     |RFToolsControl                |rftoolscontrol                |1.21-8.0.1          |Manifest: NOSIGNATURE
		rftoolsdim-1.21-12.0.3.jar                        |RFToolsDimensions             |rftoolsdim                    |1.21-12.0.3         |Manifest: NOSIGNATURE
		rftoolspower-1.21-7.0.5.jar                       |RFToolsPower                  |rftoolspower                  |1.21-7.0.5          |Manifest: NOSIGNATURE
		rftoolsstorage-1.21-6.0.4.jar                     |RFToolsStorage                |rftoolsstorage                |1.21-6.0.4          |Manifest: NOSIGNATURE
		rftoolsutility-1.21-7.0.10.jar                    |RFToolsUtility                |rftoolsutility                |1.21-7.0.10         |Manifest: NOSIGNATURE
		rightclickharvest-neoforge-4.6.0+1.21.1.jar       |Right Click Harvest           |rightclickharvest             |4.6.0+1.21.1        |Manifest: NOSIGNATURE
		rsinfinitybooster-neoforge-1.21.1-1.0.0.48.jar    |RSInfinityBooster             |rsinfinitybooster             |1.21.1-1.0.0.48     |Manifest: NOSIGNATURE
		neoforge-21.1.5.jar                               |Saecularia Caudices           |saeculariacaudices            |21.1.5              |Manifest: NOSIGNATURE
		saturn-mc1.21.1-0.1.5.jar                         |Saturn                        |saturn                        |0.1.5               |Manifest: NOSIGNATURE
		neoforge-21.1.18.jar                              |scena                         |scena                         |21.1.18             |Manifest: NOSIGNATURE
		Searchables-neoforge-1.21.1-1.0.2.jar             |Searchables                   |searchables                   |1.0.2               |Manifest: NOSIGNATURE
		SereneSeasons-neoforge-1.21.1-10.1.0.3.jar        |Serene Seasons                |sereneseasons                 |10.1.0.3            |Manifest: NOSIGNATURE
		shrink-2.0.1.47-neoforge.jar                      |Shrink                        |shrink                        |2.0.1.47            |Manifest: NOSIGNATURE
		silent-gear-1.21.1-neoforge-4.0.30.jar            |Silent Gear                   |silentgear                    |4.0.30              |Manifest: NOSIGNATURE
		silent-lib-1.21.1-neoforge-10.5.1.jar             |Silent Lib                    |silentlib                     |10.5.1              |Manifest: NOSIGNATURE
		inventorysorter-1.21.1-24.0.24.jar                |Simple Inventory Sorter       |inventorysorter               |24.0.24             |Manifest: NOSIGNATURE
		simplemagnets-1.1.12c-neoforge-mc1.21.jar         |Simple Magnets                |simplemagnets                 |1.1.12+c            |Manifest: NOSIGNATURE
		SimpleRPC-4.0.5.jar                               |Simple RPC                    |simplerpc                     |4.0.5               |Manifest: NOSIGNATURE
		simple_snowy_fix-1.21.1-1.21.10-2.1.5-neoforge.jar|Simple Snowy Fix              |simple_snowy_fix              |2.1.5               |Manifest: NOSIGNATURE
		SmartBrainLib-neoforge-1.21.1-1.16.11.jar         |SmartBrainLib                 |smartbrainlib                 |1.16.11             |Manifest: NOSIGNATURE
		smoothchunk-1.21-4.1.jar                          |Smoothchunk mod               |smoothchunk                   |4.1                 |Manifest: NOSIGNATURE
		snowundertrees-1.21.1-1.5.jar                     |Snow Under Trees              |snowundertrees                |1.5                 |Manifest: NOSIGNATURE
		sodium-neoforge-0.6.13+mc1.21.1.jar               |Sodium                        |sodium                        |0.6.13+mc1.21.1     |Manifest: NOSIGNATURE
		sodiumextras-neoforge-1.0.8-1.21.1.jar            |Sodium Extras                 |sodiumextras                  |1.0.7               |Manifest: NOSIGNATURE
		sodiumoptionsapi-neoforge-1.0.10-1.21.1.jar       |Sodium Options API            |sodiumoptionsapi              |1.0.10              |Manifest: NOSIGNATURE
		sodiumoptionsmodcompat-neoforge-1.0.0-1.21.1.jar  |Sodium Options Mod Compat     |sodiumoptionsmodcompat        |1.0.0               |Manifest: NOSIGNATURE
		sophisticatedbackpacks-1.21.1-3.25.14.1410.jar    |Sophisticated Backpacks       |sophisticatedbackpacks        |3.25.14             |Manifest: NOSIGNATURE
		sophisticatedcore-1.21.1-1.3.89.1239.jar          |Sophisticated Core            |sophisticatedcore             |1.3.89              |Manifest: NOSIGNATURE
		Sparkweave-NeoForge-0.510.0.jar                   |Sparkweave Engine             |sparkweave                    |0.510.0             |Manifest: NOSIGNATURE
		spectrelib-neoforge-0.17.2+1.21.jar               |SpectreLib                    |spectrelib                    |0.17.2+1.21         |Manifest: NOSIGNATURE
		solcarrot-1.21.1-1.16.5.jar                       |Spice of Life: Carrot Edition |solcarrot                     |1.16.5              |Manifest: NOSIGNATURE
		StorageDrawers-neoforge-1.21.1-13.11.4.jar        |Storage Drawers               |storagedrawers                |13.11.4             |Manifest: NOSIGNATURE
		Structory_Towers_1.21.x_v1.0.14.jar               |Structory: Towers             |structory_towers              |1.0.14              |Manifest: NOSIGNATURE
		structureessentials-1.21.1-4.8.jar                |Structure Essentials mod      |structureessentials           |4.8                 |Manifest: NOSIGNATURE
		structure_layout_optimizer-neoforge-1.0.11.jar    |Structure Layout Optimizer    |structure_layout_optimizer    |1.0.11              |Manifest: NOSIGNATURE
		supermartijn642configlib-1.1.8-neoforge-mc1.21.jar|SuperMartijn642's Config Libra|supermartijn642configlib      |1.1.8               |Manifest: NOSIGNATURE
		supermartijn642corelib-1.1.18a-neoforge-mc1.21.jar|SuperMartijn642's Core Lib    |supermartijn642corelib        |1.1.18+a            |Manifest: NOSIGNATURE
		supplementaries-1.21-3.5.5-neoforge.jar           |Supplementaries               |supplementaries               |1.21-3.5.4          |Manifest: NOSIGNATURE
		suppsquared-1.21-1.2.14-neoforge.jar              |Supplementaries Squared       |suppsquared                   |1.21-1.2.14         |Manifest: NOSIGNATURE
		TerraBlender-neoforge-1.21.1-4.1.0.8.jar          |TerraBlender                  |terrablender                  |4.1.0.8             |Manifest: NOSIGNATURE
		aether-1.21.1-1.5.10-neoforge.jar                 |The Aether                    |aether                        |1.5.10              |Manifest: NOSIGNATURE
		twilightforest-1.21.1-4.7.3196-universal.jar      |The Twilight Forest           |twilightforest                |4.7.3196            |Manifest: NOSIGNATURE
		tickwands-1.2.jar                                 |Tick Wands                    |tickwands                     |1.2                 |Manifest: NOSIGNATURE
		tiab-neoforge-6.5.0.jar                           |Time In A Bottle              |tiab                          |6.5.0               |Manifest: NOSIGNATURE
		titanium-1.21-4.0.40.jar                          |Titanium                      |titanium                      |4.0.40              |Manifest: NOSIGNATURE
		toofast-1.21.0-0.4.3.5.jar                        |Too Fast                      |toofast                       |0.4.3.5             |Manifest: NOSIGNATURE
		ToolBelt-1.21.1-2.2.7.jar                         |Tool Belt                     |toolbelt                      |2.2.7               |Manifest: NOSIGNATURE
		torchmaster-neoforge-1.21.1-21.1.9.jar            |Torchmaster                   |torchmaster                   |21.1.9              |Manifest: NOSIGNATURE
		totw_modded-neoforge-1.21-1.0.8.jar               |Towers of The Wild: Modded    |totw_modded                   |1.0.8               |Manifest: NOSIGNATURE
		t_and_t-neoforge-fabric-1.13.7+1.21.1.jar         |Towns and Towers              |t_and_t                       |1.13.7              |Manifest: NOSIGNATURE
		TRansition-1.0.8-1.21.1-neoforge-SNAPSHOT.jar     |TRansition                    |transition                    |1.0.8               |Manifest: NOSIGNATURE
		transparent-neoforge-21.1.0.jar                   |Transparent                   |transparent                   |21.1.0              |Manifest: NOSIGNATURE
		trashcans-1.0.18c-neoforge-mc1.21.jar             |Trash Cans                    |trashcans                     |1.0.18+c            |Manifest: NOSIGNATURE
		treasuredistance-1.0.jar                          |Treasure Distance             |treasuredistance              |1.0                 |Manifest: NOSIGNATURE
		TRender-1.0.8-1.21.1-neoforge-SNAPSHOT.jar        |TRender                       |trender                       |1.0.8               |Manifest: NOSIGNATURE
		txnilib-neoforge-1.0.24-1.21.1.jar                |TxniLib                       |txnilib                       |1.0.24              |Manifest: NOSIGNATURE
		universalgrid-neoforge-1.21.1-0.2.3.jar           |Universal Grid                |universalgrid                 |1.21.1-0.2.3        |Manifest: NOSIGNATURE
		VisualWorkbench-v21.1.1-1.21.1-NeoForge.jar       |Visual Workbench              |visualworkbench               |21.1.1              |Manifest: NOSIGNATURE
		vuc-1.3.0-neoforge-1.21.1.jar                     |VUC - Very Useful Commands    |vuc                           |1.3.0               |Manifest: NOSIGNATURE
		waystones-neoforge-1.21.1-21.1.24.jar             |Waystones                     |waystones                     |21.1.24             |Manifest: NOSIGNATURE
		DungeonsArise-1.21.1-2.1.68-release.jar           |When Dungeons Arise           |dungeons_arise                |2.1.68              |Manifest: NOSIGNATURE
		WitherSkeletonTweaks-1.21.1-10.1.1.jar            |Wither Skeleton Tweaks        |wstweaks                      |10.1.1              |Manifest: NOSIGNATURE
		wits-1.3.0+1.21-neoforge.jar                      |WITS                          |wits                          |1.3.0+1.21-neoforge |Manifest: NOSIGNATURE
		worldstripper-1.21-5.0.0-neoforge.jar             |World Stripper                |worldstripper                 |5.0.0               |Manifest: NOSIGNATURE
		worldedit-mod-7.3.8.jar                           |WorldEdit                     |worldedit                     |7.3.8+6939-7d32b45  |Manifest: NOSIGNATURE
		xnet-1.21-7.0.6.jar                               |XNet                          |xnet                          |1.21-7.0.6          |Manifest: NOSIGNATURE
		xptome-1.21.1-2.4.jar                             |XP Tome                       |xpbook                        |2.4                 |Manifest: NOSIGNATURE
		ZeroCore2-1.21.1-2.4.20.jar                       |Zero CORE 2                   |zerocore                      |1.21.1-2.4.20       |Manifest: NOSIGNATURE
	Crash Report UUID: ecbb5019-4b47-417b-be83-d984c79c64a9
	FML: 4.0.42
	NeoForge: 21.1.216
	Flywheel Backend: flywheel:off
