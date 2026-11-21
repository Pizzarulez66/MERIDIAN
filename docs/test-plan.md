# 0.2.0 acceptance test plan

## A. Installation and startup
- [ ] Import the candidate package into a clean launcher instance.
- [ ] Confirm Minecraft 1.21.1 and NeoForge 21.1.249.
- [ ] Confirm Java 21.
- [ ] Launch to title screen twice.
- [ ] Confirm no missing dependency or duplicate-mod errors.
- [ ] Confirm the client-only set is absent from the dedicated-server profile.

## B. Core mod regression
- [ ] Load a copy of the existing 0.1.0 test world.
- [ ] Enter and exit a world.
- [ ] Open Mekanism machine GUIs.
- [ ] Open Immersive Engineering machine GUIs.
- [ ] Test IE power distribution and Mekanism energy use.
- [ ] Test item and fluid transfer.
- [ ] Confirm recipes remain visible in JEI.

## C. QoL
- [ ] Jade overlays show useful information without excessive clutter.
- [ ] Mouse Tweaks works in player, chest and machine inventories.
- [ ] Controlling search finds conflicting keybinds.
- [ ] AppleSkin displays food information correctly.
- [ ] Xaero maps and waypoints persist after relaunch.
- [ ] Shulker tooltip and enchantment descriptions display correctly.

## D. Performance
- [ ] Compare baseline and candidate FPS in the same test location.
- [ ] Compare frame-time spikes, not only average FPS.
- [ ] Compare title-to-world load time.
- [ ] Compare RAM after 5, 15 and 30 minutes.
- [ ] Check for rendering artifacts on IE multiblocks and Mekanism machines.
- [ ] Test with culling mods enabled, then disabled if visual issues appear.

## E. Diagnostics
- [ ] Confirm Spark commands work on client and integrated server.
- [ ] Generate and open one Spark report.
- [ ] Confirm Observable loads and can profile a test block entity, if included.
- [ ] Confirm crash reporting remains available and original logs are preserved.

## Release gate
Do not call 0.2.0 stable until all critical tests pass. If a mod causes a regression, remove or defer that mod rather than compromising the known-good 0.1.0 base.
