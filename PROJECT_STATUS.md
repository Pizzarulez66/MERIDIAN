# Project status

**Release track:** 0.1.0 design scaffold  
**Last research pass:** 2026-11-21  
**Target:** Minecraft 1.21.1 / NeoForge 21.1.x / Java 21+

## Completed in this pass

- Selected a viable target platform based on current primary-mod and tooling releases.
- Defined distinct roles for Mekanism and Immersive Engineering.
- Designed the multi-district MERIDIAN endgame.
- Identified a scripting route for Mekanism machine recipes and an IE KubeJS compatibility candidate.
- Documented version/dependency constraints and a staged validation plan.
- Created a repository-ready documentation and KubeJS scaffold.

## Not yet completed

- No in-game launch, world-generation, or dedicated-server test has been run.
- No modpack manifest has been frozen; exact launcher dependency resolution remains to be done.
- No recipe changes have been enabled. Cross-mod recipe IDs, item IDs, machine schemas, and balance must be confirmed in the target build first.
- The FTB Quests book has not yet been generated.
- The target GitHub repository could not be read or written through the currently connected GitHub integration: the authenticated account was identified, but the integration reported no installed repository access and the target repository lookup returned 404. This scaffold is therefore supplied as a downloadable project archive rather than being represented as a pushed commit.

## Next milestones

- [ ] M1 — Build a minimal client and dedicated server; confirm clean boot and join.
- [ ] M2 — Validate IE ↔ Mekanism FE transfer in both directions and record practical throughput/loss.
- [ ] M3 — Validate IE mineral output through Mekanism 3x/4x processing, and Mekanism products through IE fabrication machines.
- [ ] M4 — Add the first 8–12 cross-mod recipes and lock progression.
- [ ] M5 — Author FTB Quests chapters and self-audit tasks.
- [ ] M6 — Balance the MERIDIAN project bill of materials and publish a test build.
