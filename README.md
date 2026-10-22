# Roadster Flight 0.9.4

An unofficial Roadster driving and flight mod for **Over the Hill**, for **Windows 64-bit**.

Drive the Roadster normally, jump and hold for roof-direction lift, boost, and air-roll. The title screen has a **MODS: ON / OFF** switch. The Roadster is the only added vehicle in this release.

Version 0.9.4 restores keyboard flight input and handles shared controller buttons during Roadster gameplay while preserving your saved bindings. The LT / L2 air-roll chord is unchanged.

The package owner has confirmed permission to include the supplied Roadster model and texture. See [MODEL-CREDITS.md](MODEL-CREDITS.md) for the permission record and asset credits.

## Install

Read [INSTALL.md](INSTALL.md). Manual copying is the primary route. BepInEx is a separate prerequisite and is not bundled.

## Controls

Keyboard airborne pitch/yaw use your native throttle, brake and steering bindings. Extra keyboard defaults:

| Action | Default |
| --- | --- |
| Jump; hold for roof-direction thrust | Space |
| Rear boost | Left Shift |
| Air roll left | Left Arrow |
| Air roll right | Right Arrow |
| Assisted flight | F6 |

Headlights use the native game action (**H** by default), including any native rebind. Rebind the five added rows under **Settings > Controls > Basic > Keyboard & Mouse**. Keyboard non-movement conflicts are temporarily moved while the mod car owns input, then restored in menus or stock mode. The camera eases between ground and air framing over about 1.2 seconds.

For controller pitch, pull the **left stick back** for nose-up or push it **forward** for nose-down. These have separate rebindable pitch actions, independent of RT / LT and ground driving. For air-roll, hold **LT / L2** while airborne and move the **left stick left or right**; pitch and roll work together. The chord uses physical stick X regardless of steering rebinds and replaces yaw while held. Ground braking and steering stay native.

The **Controller** Basic controls list has six Roadster rows: jump / roof thrust, boost, assisted flight, **Air roll modifier (hold + steer)**, pitch up and pitch down. The modifier defaults to LT / L2; pitch defaults to left-stick down / up. The other three extras preserve existing preferences or start unassigned. Keyboard arrow-key roll and the five keyboard rows stay unchanged.

Assign your controller extras in that native screen. Rebinding an ordinary extra to an occupied input uses the native swap behavior and can leave its previous stock action unassigned; review affected rows. Native headlights remain available (**D-pad left** by default). [INSTALL.md](INSTALL.md) covers the full keyboard controls, controller chord and rebinding.

Noncritical native controller bindings sharing Roadster buttons are now suspended only while Roadster gameplay owns input, then restored exactly before Settings, in menus, on mod-off and detach. Saved stock/controller preferences are preserved. Movement, reset and Pause remain protected; the air-roll modifier may share Brake.

Use **MODS: OFF** at the title before stock co-op. It restores stock selection/inventory and controls, and removes this mod's extra prefab identities. The switch affects this plugin, not BepInEx or other mods. The custom Roadster is solo-only; two-peer co-op compatibility requires a native test and is not guaranteed by managed tests.

## Updating and removing

The internal DLL filename and plugin ID remain stable for upgrades. Keep only one `OverTheHill.RocketVehicles.dll` in `BepInEx/plugins`. Do not keep a renamed copy of the previous plugin alongside it.

Settings, Roadster progress sidecars and added control rebinds stay in `BepInEx/config`. The release contains no personal configuration, saves, full native logs, source assets or old plugin DLLs. [INSTALL.md](INSTALL.md) covers manual removal and optional scripts.

See [CHANGELOG.md](CHANGELOG.md), [MODEL-CREDITS.md](MODEL-CREDITS.md), and `THIRD-PARTY-NOTICES.txt`. Build identity and included file hashes are in `MANIFEST.json` and `SHA256SUMS.txt`.
