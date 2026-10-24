# Install — Windows x64 / Windows game through Proton

1. Close Over the Hill. In Steam, open **Properties → Installed Files → Browse**.
2. Install the separate **BepInEx 6 Unity.IL2CPP-win-x64** loader beside `over the hill.exe`. Follow the [official IL2CPP guide](https://docs.bepinex.dev/master/articles/user_guide/installation/unity_il2cpp.html). This mod uses BepInEx build **6.0.0-be.789**; BepInEx is not bundled.
3. Launch once so BepInEx generates its files, then close the game. This first run can take longer.
4. Extract this release ZIP, then copy its `BepInEx` folder into the game folder. The final plugin path is:

   `BepInEx/plugins/RocketVehicles/OverTheHill.RocketVehicles.dll`

5. Start the game, set **MODS: ON** at the title, and select Roadster in the normal Garage.

When updating, back up the previous DLL outside `BepInEx/plugins`, then replace it. Keep only one copy of `OverTheHill.RocketVehicles.dll`; a renamed old copy can also load. Keep your existing settings and saves. Do not copy the `Source` folder into the game.

Only the original white Roadster is included. Progress from the removed colored variants transfers to it automatically, retaining the best odometer/count and combined tool unlocks. No save reset is needed.

## Multiplayer

Both players install **Roadster Flight 0.10.6** and enable **MODS: ON** before hosting or joining. Update both computers: this build adds thrust input and uses multiplayer protocol 2. Use matching game versions and the same vehicle mods. The mod refuses mismatched versions/protocols.

If you run the Windows game through Proton, copy this ZIP's `BepInEx` folder over your existing working Windows loader setup. Windows PowerShell scripts are optional and are not needed on Linux. This package does not install a native Linux loader.

Use the normal **Multiplayer** menu to host a world and invite/join your friend. Both players can choose the Roadster in the native Garage. The release ZIP includes MULTIPLAYER-TEST.md for the first two-player check. There is no separate mod server to run.

For friends without this mod, return to the title and choose **MODS: OFF** before creating/joining their session. This turns off Roadster Flight; it does not disable BepInEx or other installed mods.

## Controls

| Action | Keyboard default |
| --- | --- |
| Drive; airborne pitch/yaw | WASD, following the game's movement rebinds |
| Jump; immediate held thrust toward the roof | Space |
| Held thrust toward the underside, using the side jets | Left Ctrl |
| Rear boost | Left Shift |
| Air roll | Left / Right Arrow |
| Flight assistance | F6 |
| Headlights | Native game action, H by default |

The Roadster has one jump per landing. Holding Space applies thrust in the direction the roof faces immediately, without a hold delay or collision-bump lockout; release to stop. Holding Ctrl applies thrust toward the underside using the existing side jets. No top-mounted boosters are added.

Use the normal camera look control to look upward while keeping the Roadster centered. In clear air, the camera can orbit below the car for up to 55 degrees of upward view. Near the ground, walls or ceilings, camera clearance limits the angle. This adds no new binding and retains zoom and the smooth flight transition.

Change the six extra keyboard bindings under **Settings → Controls → Basic → Keyboard & Mouse**, including **Thrust toward underside**. Change movement and headlights in the game's existing rows.

Under **Basic → Controller**, bind **Jump / hold roof thrust**, **Boost**, **Toggle assisted flight**, and **Thrust toward underside** to your preferred buttons. These four start unassigned on a new installation. The seven controller rows also include **Pitch up/down**, which default to left stick back/forward, and **Air roll modifier**, which defaults to LT/L2: hold it while airborne and move the left stick left/right. Pitch and roll work together. No extra controller chord is assigned for underside thrust.

Ctrl normally belongs to native gear-down. While driving Roadster, the mod's reversible binding lease moves that conflicting action to an unused key, reported in the binding summary, so both actions remain distinct. Opening settings, choosing a stock car, or turning the mod off restores the original native binding. Your saved controls are preserved.

Review native rows after assigning a button that was already used: the game's normal binding swap may leave its previous action unassigned. Essential movement, reset, and Pause inputs are protected; the roll modifier deliberately shares the brake trigger.

## Disable or remove

Use **MODS: OFF** on the title for stock sessions. To remove the plugin, close the game and delete only:

`BepInEx/plugins/RocketVehicles/OverTheHill.RocketVehicles.dll`

Leave `BepInEx/config`, your game saves, and other plugins in place. This preserves control rebinds and Roadster progress for a later reinstall.

## Optional scripts

Manual copying is enough. From PowerShell in the extracted package, you can instead run:

```powershell
.\Install.ps1 -GameDir "D:\SteamLibrary\steamapps\common\over the hill"
.\Uninstall.ps1 -GameDir "D:\SteamLibrary\steamapps\common\over the hill"
```

Use your actual game path. The scripts verify the DLL, preserve settings/saves, and put backups outside `plugins`. `-WhatIf` previews the action. If Windows blocks unsigned scripts, use manual installation; no execution-policy change is needed.

If the mod does not appear, check the plugin path, BepInEx IL2CPP x64 installation, and duplicate DLLs. Game or loader updates can require a mod update. Review local BepInEx loading errors before sharing logs containing personal paths.
