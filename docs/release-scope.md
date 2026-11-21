# Release scope

## MERIDIAN 0.2.0 — Performance, QoL & Diagnostics

Combine the former 0.1.1, 0.1.2 and 0.1.3 scopes into one update.

### Performance foundation
- ModernFix — memory, loading and general fixes.
- FerriteCore — memory reduction.
- Sodium — client rendering performance; do not pair with Embeddium.
- ImmediatelyFast — client UI/immediate rendering.
- Entity Culling — hide occluded entities/block entities; test carefully.
- More Culling — additional client-side culling; requires Cloth Config.
- Dynamic FPS — reduce resource usage while unfocused.
- Lithium — candidate only; exact 1.21.1 NeoForge file and compatibility must be confirmed before inclusion.

### Everyday QoL
- JEI — recipes and usage.
- Jade — block and machine information.
- Mouse Tweaks — inventory handling.
- AppleSkin — hunger/saturation display.
- Controlling — searchable keybinds.
- Xaero's Minimap and Xaero's World Map — navigation and waypoints.
- Shulker Box Tooltip — inspect storage contents.
- Enchantment Descriptions — in-game enchantment explanations.

### Diagnostics
- spark — primary client/server CPU and tick profiler.
- Observable — candidate block-entity profiler; validate the NeoForge artifact and dependencies before inclusion.
- Not Enough Crashes — improved crash screen/reporting; retain original logs and crash reports.

## Explicit exclusions for this release
- No C2ME in the initial baseline.
- No simultaneous Sodium + Embeddium.
- No duplicate renderer replacements.
- No speculative "fix" mods added without a reproducible reason.
- No client-only mods copied into a dedicated-server pack.

## Hardware target
Keep the pack comfortable on a Windows 11 laptop with a GTX 1650 4 GB and approximately 8 GB system RAM. Target a Minecraft heap around 3–4 GB, then adjust only from measured results. Avoid allocating nearly all physical RAM to Java.
