# Validation plan

Do not progress-lock recipes until the following tests pass on the exact frozen mod list.

## M1 — Clean platform boot

- [ ] Install the exact Minecraft 1.21.1 + NeoForge 21.1.x + Java 21 combination.
- [ ] Launch a clean client with the core mods and scripting stack.
- [ ] Launch a clean dedicated server with the same gameplay mods.
- [ ] Join the dedicated server from the client and create a new world.
- [ ] Capture `latest.log`, mod list, and server log for the baseline.

## M2 — Energy interoperability

- [ ] IE generator → IE connector/relay/wire → Mekanism Universal Cable → Mekanism machine.
- [ ] Mekanism generator/cable → supported IE input/connector route → IE machine.
- [ ] Test direct adjacency separately from wire-network transfer.
- [ ] Record transfer rate, any losses, and any sided/connector restrictions.
- [ ] Verify behavior on dedicated server, not only an integrated world.

## M3 — Item and machine interoperability

- [ ] IE Excavator output can be buffered and fed into the intended Mekanism processing stage.
- [ ] Mekanism processing outputs can be routed into the selected IE machine.
- [ ] Verify all item IDs, recipe types, tags, byproducts, and recipe-viewer visibility.
- [ ] Confirm that there is no duplicate/looping recipe or easy bypass of the intended tier.
- [ ] Test recipe outputs after restart and on a dedicated server.

## M4 — Scripting and questing

- [ ] KubeJS and Rhino load on client and server without script exceptions.
- [ ] KubeJS Mekanism loads against the selected Mekanism version.
- [ ] Immersive Engineering JS loads on NeoForge 1.21.1 if selected; if not, use IE native data recipes with validated JSON schemas.
- [ ] One test recipe is added to a Mekanism machine and one to an IE machine.
- [ ] FTB Quests, FTB Library, FTB Teams, and Architectury API load on both sides.
- [ ] A test quest correctly detects one item task and one manual/self-audit task.

## M5 — Balance and performance

- [ ] Measure baseline idle and factory-active memory/CPU.
- [ ] Test a small factory, then a representative full district, then all four districts chunk-loaded.
- [ ] Check chunk loading, item entity counts, transporter/conveyor pathing, and energy-network performance.
- [ ] Review all ore multiplication paths and byproduct loops.
- [ ] Tune machine time, energy, chemical costs, excavator yield, and fuel supply only after measuring.

## M6 — Release candidate

- [ ] Export a launcher manifest with exact file IDs/versions.
- [ ] Verify a fresh client install from the export.
- [ ] Verify a fresh dedicated server from the same manifest.
- [ ] Confirm client/server mod parity and no missing configs/scripts/quest data.
- [ ] Publish known issues, exact loader version, Java version, and checksum of the release archive.
