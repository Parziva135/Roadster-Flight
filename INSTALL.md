# Install Roadster Flight 0.9.4 — Windows 64-bit

## 1. Find the game folder

Close Over the Hill. In Steam, open **Properties > Installed Files > Browse**. Use the folder containing `over the hill.exe`. Your Steam library can be on any drive.

## 2. Install the separate BepInEx prerequisite

Follow the [official Unity IL2CPP installation guide](https://docs.bepinex.dev/master/articles/user_guide/installation/unity_il2cpp.html). Download **Unity.IL2CPP-win-x64**, extract its contents into the game root beside the executable, then launch once to generate configuration and interop files. The first IL2CPP run can take longer. Close the game afterward.

This mod was developed against **BepInEx 6.0.0-be.789**. The [official build page](https://builds.bepinex.dev/projects/bepinex_be) lists that build and newer ones; the official [tested-build archive link](https://builds.bepinex.dev/projects/bepinex_be/789/BepInEx-Unity.IL2CPP-win-x64-6.0.0-be.789%2B6cea286.zip) is provided for convenience. A newer loader is not automatically a tested combination. Use the Windows x64 IL2CPP archive, not the Mono, x86 or BepInEx 5 package.

The expected prerequisite marker is `BepInEx/core/BepInEx.Unity.IL2CPP.dll`. BepInEx is not included in this release. These instructions were checked against the official guide/build index on 2026-10-22.

## 3. Manual installation — recommended

1. Extract the Roadster Flight ZIP into a temporary folder.
2. If upgrading, make a local copy of the existing `BepInEx/plugins/RocketVehicles/OverTheHill.RocketVehicles.dll` before replacing it.
3. Copy the release's `BepInEx/plugins/RocketVehicles` folder into the game's `BepInEx/plugins` folder. The final path must be `BepInEx/plugins/RocketVehicles/OverTheHill.RocketVehicles.dll`.
4. Keep a single copy of this plugin DLL. Do not copy the README, source models or other release folders into `plugins`.
5. Start the game. The title should contain one **MODS: ON / OFF** row below Settings. Enable mods for the solo Roadster; choose OFF for stock mode.

Existing settings, saves and sidecars should stay in place. The legacy DLL name and plugin ID are deliberately unchanged to replace prior versions in place.

The 0.9.4 input recovery keeps existing keyboard and controller rebinds. Keep your current `RocketVehicles.controls.json` sidecar in place when upgrading.

## Drive, fly and use the lights

Select the Roadster in the native Garage while **MODS: ON** is enabled. Movement and headlights continue to use your native game bindings. The table below lists keyboard defaults; controller setup follows it.

| Action | Default | How it works |
| --- | --- | --- |
| Throttle / reverse; airborne pitch | W / S | Uses native movement bindings. |
| Steering; airborne yaw | A / D | Uses native steering bindings. |
| Jump; hold for lift | Space | One jump per landing. Keep holding to engage the underside lift jets; thrust follows the roof direction, including while rolled. Release to stop lift. |
| Rear rocket boost | Left Shift | Hold for forward boost from the rear outlets. |
| Air roll left | Left Arrow | Hold while airborne; the side jets follow the roll input. |
| Air roll right | Right Arrow | Hold while airborne. |
| Assisted flight | F6 | Toggle hover / flight assistance. |
| Headlights | H | Uses the game's native headlight action and your native rebind; the mod does not reserve or override H. |

Change keyboard bindings at **Settings > Controls > Basic > Keyboard & Mouse**. The five added rows are **Jump / hold roof thrust**, **Boost**, **Air roll left**, **Air roll right** and **Toggle assisted flight**. Rebind movement and headlights through the game's existing rows.

### Set up a controller

While airborne, pull the **left stick back** for nose-up pitch, or push it **forward** for nose-down pitch. Hold **LT / L2** and move the **left stick left or right** to air-roll. Pitch and roll can be combined. Ground driving keeps your native throttle, brake and steering bindings; LT / L2 brakes by default.

Controller pitch has its own bindings and is independent of RT / LT and the native ground-driving actions. RT / LT no longer also pitch the car. During the roll chord, stick X controls roll instead of yaw while the pitch bindings stay available. Release LT / L2 to return to normal airborne yaw.

The chord always uses the physical left stick horizontally, even if you change the native ground-steering binding. Your normal driving and airborne yaw still use the native steering action outside the chord.

The Controller tab has six Roadster rows:

| Roadster controller action | Initial default |
| --- | --- |
| Jump / hold roof thrust | Unassigned |
| Boost | Unassigned |
| Toggle assisted flight | Unassigned |
| Air roll modifier (hold + steer) | Left trigger (LT / L2); combine with left-stick X while airborne |
| Pitch up | Left stick down / pull back |
| Pitch down | Left stick up / push forward |

1. Open **Settings > Controls > Basic > Controller** and find the six Roadster rows.
2. Bind jump / roof thrust, boost and assisted flight to the controller inputs you want to use. To change LT / L2, select **Roadster — Air roll modifier (hold + steer)**. Use the two pitch rows to choose different controller inputs for nose-up and nose-down. Your keyboard bindings remain separate; the keyboard still has its two arrow-key roll rows.
3. Review affected native rows after rebinding an occupied input. Native swaps for ordinary Roadster actions can leave the previous stock action **unassigned** when the Roadster slot was empty. Choose a different input or rebind that stock action if you want to retain it.
4. Leave Settings to save and return to your Roadster.

Ordinary Roadster controller actions cannot capture the game's movement, vehicle reset or Pause inputs. The dedicated air-roll modifier intentionally shares LT / L2 with native braking, with roll limited to airborne use. If another choice is refused, select a different input so essential native controls remain available.

Rebinding the modifier preserves stock bindings. While Roadster gameplay owns input, noncritical native controller actions that share your configured Roadster buttons are temporarily suspended so one press does not trigger both actions. Their exact bindings are restored before Settings, in menus, on **MODS: OFF**, and when the Roadster detaches. This temporary conflict handling does not rewrite your saved stock/controller preferences. Movement, vehicle reset and Pause stay protected; only the modifier may deliberately share native Brake.

Existing jump / boost / assisted-flight preferences carry over. The previous separate controller roll bindings stay in saved data but no longer drive controller roll; use the new modifier row. Keyboard roll preferences are unchanged.

Native steering and throttle / brake still drive normal ground movement. Outside the roll chord, the native steering action provides controller airborne yaw; the separate pitch rows provide controller pitch. Keyboard W / S pitch is unchanged. Headlights remain on the game's existing headlight action (**D-pad left** by default), including your rebind; this is not an extra Roadster row.

The keyboard conflict lease temporarily moves conflicting non-movement bindings only while the mod owns Roadster driving input. Native controls are restored in menus or **MODS: OFF**. Conflicts with protected controls still require a different binding. Controller changes you deliberately make in Settings remain your saved native preferences. The camera eases between ground and air framing over about 1.2 seconds. At the title, **MODS: OFF** restores stock selection, inventory and controls, and removes this mod's extra prefab identities. It does not switch off BepInEx or other plugins. Use stock mode before co-op; two-peer co-op compatibility has not been established by managed tests.

## Optional installer

The script copies only this plugin DLL, backs up a previous DLL outside `plugins`, verifies SHA256 and writes a local install receipt. It does not download BepInEx, change saves or install other dependencies.

From a PowerShell opened in the extracted release folder:

```powershell
.\Install.ps1 -GameDir "D:\SteamLibrary\steamapps\common\over the hill"
```

Supply your actual game path. No global execution-policy change or forced administrator launch is required. If your policy blocks unsigned scripts, use manual installation. `-WhatIf` previews the intended operation. The installer refuses a running game, missing IL2CPP loader, corrupt payload or duplicate legacy DLL in another plugin folder.

## Uninstall

Close the game. Remove only `BepInEx/plugins/RocketVehicles/OverTheHill.RocketVehicles.dll`. Leave BepInEx, other plugins, `BepInEx/config`, saves and sidecars intact. You can keep `RocketVehicles.controls.json` and `RocketVehicles.garage.*.json` for a later reinstall.

Alternatively:

```powershell
.\Uninstall.ps1 -GameDir "D:\SteamLibrary\steamapps\common\over the hill"
```

The optional uninstaller verifies the installed DLL matches this release, makes a local backup, and removes only that DLL and its own install receipt. A mismatched version requires its matching uninstaller or manual removal. Backups under `BepInEx/RoadsterFlight-backups` are never loaded as plugins.

## If the mod does not load

Check the final DLL path, the Windows x64 IL2CPP prerequisite, and that only one copy is installed. BepInEx's own log location can vary by build (`LogOutput.log` / `LogOutput.txt`); inspect its loading errors locally. Do not share full logs containing profile paths without reviewing/redacting them. Game or loader updates can require a compatible mod update.
