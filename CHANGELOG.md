# Changelog

## 0.9.4 — Flight input recovery

- Restores keyboard flight actions that could remain unresponsive despite showing their assigned bindings.
- Adds separate controller pitch-up / pitch-down bindings, defaulting to left-stick back / forward. They work alongside LT + stick-X roll and keep controller pitch independent of ground throttle/brake.
- Temporarily resolves noncritical native controller conflicts while Roadster gameplay owns input, then restores exact native bindings in Settings, menus, stock mode and detach.
- Preserves protected movement, vehicle reset and Pause bindings, and the LT + left-stick air-roll chord.
- Preserves saved keyboard/controller bindings and stock preferences. The user confirmed the keyboard recovery works; physical controller pitch flight remains a manual check. See VALIDATION.txt for the completed build, input, native menu and installer checks.

## 0.9.3 — LT + stick air roll

- Adds an airborne controller air-roll chord: hold LT and steer with left-stick X to roll.
- Replaces the separate controller roll-left / roll-right rows with one Air roll modifier row; keyboard arrow-key roll stays unchanged.
- Uses physical left-stick X for the chord even after steering rebinds; suppresses yaw and brake-based pitch while retaining throttle-based pitch. Modifier rebinding preserves stock bindings.
- Preserves normal ground braking and the controller/headlight/title fixes confirmed by the user.
- Updates the controller setup guide with the modifier row, its airborne behavior, and unchanged keyboard controls. Final validation is recorded separately in VALIDATION.txt.

## 0.9.2 — Controller bindings

- Adds native controller rebinding for Roadster jump / roof thrust, rear boost, air roll and assisted flight.
- Preserves the keyboard defaults and native movement/headlight actions.
- Includes the headlight placement and visible title MODS switch fixes confirmed by the user after 0.9.1.
- Controller extras start unassigned and use the native rebinding screen; existing movement and headlights keep their native bindings. Controller conflicts require explicit rebinding.
- Adds controller setup and rebinding instructions to the install guide. Final validation is recorded separately in VALIDATION.txt.

## 0.9.1 — Local headlight/title test build

- Places the native headlights at the Roadster's actual headlamp housings, while retaining the game's headlight toggle and rebind.
- Repairs the title-screen MODS switch placement and lifecycle so its native-style ON / OFF control is visible at the title.
- Adds the complete driving, flight and native-headlight controls directly to the installation guide.
- Retains the model, texture, wheels, glass, driving and flight controls from 0.9.0. See VALIDATION.txt for the final build and native checks actually completed.

## 0.9.0 — Roadster-only release

- Roadster-only release: the former second vehicle, its garage icon and its active catalog/visual registration are removed. Legacy saved references are handled by the upgrade path.
- Public-facing name becomes **Roadster Flight**. The internal plugin ID and DLL filename stay unchanged for in-place upgrades.
- Retains native Garage integration, title MODS switch, five native Controls rows, driving, jump/held roof thrust, rear boost, roll jets and eased camera framing.
- Lean distribution contains the runtime DLL, install/removal instructions, optional portable scripts, checksums and required credits. It does not contain old combined releases, source/designer assets or personal state.

Model/texture redistribution permission was confirmed by the package owner on 2026-10-22; see MODEL-CREDITS.md. The release is prepared locally and has not been published. Runtime validation details are recorded in VALIDATION.txt and the release manifest/status, without claiming unperformed native or multiplayer tests.
