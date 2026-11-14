# FPS Client — Fabric 1.21.11

## Build
- Install a Java 21 JDK.
- Open this folder as a Gradle project in IntelliJ IDEA or another Java IDE.
- Run `gradle build` (or `./gradlew build` after generating a Gradle wrapper).
- The mod jar is created in `build/libs/`.

## Install
Copy the jar into `.minecraft/mods/`. Install Fabric Loader for Minecraft 1.21.11 and a matching Fabric API.

## Controls
Press **Right Shift** to open/close the ClickGUI. Click a module row to toggle it; drag the title bar to move the panel. FPS appears in the top-left.

## Implemented behavior and notes
- Entity / Distance Optimizer lowers the client's configured render distance to at most 8 chunks and restores the previous value when disabled. Vanilla performs its normal frustum culling; this module does not implement custom occlusion queries.
- Particle Limiter cancels client particle insertion while enabled.
- Fog & Sky Optimizer disables clouds and restores the previous cloud setting when disabled. It does not remove terrain fog; changing fog can affect visibility and is intentionally not hooked here.
- Module states are saved to `.minecraft/config/fpsclient.json`.

The project uses official Mojang mappings for Minecraft 1.21.11. Fabric's guidance recommends Mojang mappings for this final obfuscated Minecraft release.
