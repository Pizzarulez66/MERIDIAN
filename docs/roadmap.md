# Development Roadmap

## Milestone 0 — Design and technical foundation
**Goal:** Turn the concept into a testable project baseline.

Tasks:
- [ ] Confirm Minecraft 1.21.1 NeoForge as target.
- [ ] Verify exact Mekanism and Immersive Engineering builds and dependencies.
- [ ] Create a clean minimal client instance.
- [ ] Create a clean dedicated server instance.
- [ ] Select the quest system.
- [ ] Evaluate a scripting route and document its limits.
- [ ] Establish a locked mod manifest and known-good backup.
- [ ] Measure idle and active memory/performance.
- [ ] Confirm the Core component identities and campaign acts.

**Exit criteria:** Clean client and server boot, world creation, save/reload, and multiplayer join all work with the core mods.

## Milestone 1 — Industrial vertical slice
**Goal:** Prove that the two core mods form a meaningful progression loop.

Tasks:
- [ ] Implement one early IE-focused chain.
- [ ] Implement one Mekanism-focused chain.
- [ ] Implement at least two cross-mod chains.
- [ ] Verify automation and logistics for each.
- [ ] Test recipe visibility and quest tracking.
- [ ] Measure plausible production time and power cost.
- [ ] Confirm no unintended recipe bypass.

**Exit criteria:** A player can progress from basic resources to a small automated industrial setup with both pillars contributing.

## Milestone 2 — Campaign and progression
**Goal:** Build the full Overworld campaign.

Tasks:
- [ ] Implement Acts I–IV.
- [ ] Build the four district chapters.
- [ ] Add contracts, diagrams, and clear sourcing hints.
- [ ] Implement sustainable supply routes for bulk materials.
- [ ] Add the five Meridian component chapters.
- [ ] Balance costs against realistic automation.

**Exit criteria:** The player can reach the Meridian Project through coherent, testable progression.

## Milestone 3 — Meridian Core and Gate prototype
**Goal:** Make the endgame mechanically real.

Tasks:
- [ ] Implement five component items.
- [ ] Implement the Meridian Core recipe and quest chapter.
- [ ] Prototype Gate controller/activation.
- [ ] Choose existing destination vs custom dimension.
- [ ] Test activation, persistence, multiplayer, and failure cases.
- [ ] Add audiovisual feedback and a clear first-arrival experience.

**Exit criteria:** A player can craft the Core, complete the Gate project, activate it, and reach the destination reliably.

## Milestone 4 — Frontier and post-game
**Goal:** Give the destination meaningful reasons to explore and build.

Tasks:
- [ ] Design frontier resources and their uses.
- [ ] Add structures and recoverable technology.
- [ ] Add outpost and logistics objectives.
- [ ] Add optional second-generation engineering projects.
- [ ] Ensure the main campaign is already complete before post-game quotas.

**Exit criteria:** The destination supports a distinct optional gameplay loop without destabilizing the main campaign.

## Milestone 5 — Release hardening
**Goal:** Deliver a reproducible, multiplayer-ready pack.

Tasks:
- [ ] Full client and dedicated-server regression tests.
- [ ] Fresh world and existing save tests.
- [ ] Quest sync and progression persistence tests.
- [ ] Performance tests on target hardware.
- [ ] Final mod manifest and dependency audit.
- [ ] Known-issues list and installation instructions.
- [ ] Release notes and versioned backup.

**Exit criteria:** All critical validation checks pass; no known progression blockers or server-start failures remain.

## Scope control

If a feature threatens stability or performance, defer it rather than compromising the core campaign. The custom dimension is explicitly allowed to move later in the schedule.
