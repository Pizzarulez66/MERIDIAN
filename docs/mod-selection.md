# Mod Selection and Compatibility Policy

## Status vocabulary

- **Core:** Required to express the pack's identity.
- **Candidate:** Promising, but not yet validated for the exact target.
- **Optional:** Adds a useful route or convenience but is not required for the main campaign.
- **Deferred:** Intentionally postponed until the foundation works.
- **Rejected:** Tested or reviewed and excluded, with a recorded reason.

Nothing below should be treated as a final version lock.

## Core pillars

| Mod | Status | Intended responsibility |
|---|---|---|
| Mekanism | Core | Advanced ore processing, chemical systems, factories, materials, and utilities |
| Immersive Engineering | Core | Coke/steel, heavy fabrication, multiblocks, visible infrastructure, and material handling |

Exact NeoForge 1.21.1 files, dependencies, and server compatibility must be verified before creating the locked manifest.

## Support categories to evaluate

| Category | Candidate direction | Acceptance criteria |
|---|---|---|
| Quests | FTB Quests ecosystem | Correct 1.21.1 NeoForge builds; stable item/recipe objectives; multiplayer sync |
| Scripting | KubeJS and required integrations | Exact loader support; recipe coverage for both pillars; server-side correctness |
| IE expansion | Immersive Petroleum or other IE addons | Adds useful industrial roles without bloating progression |
| Mekanism expansion | Official/compatible Mekanism addons | Correct version and dependency chain; no duplicate or obsolete progression |
| Storage | AE2 or a lighter alternative | Optional convenience; must not erase logistics gameplay or exceed performance budget |
| Logistics | Conveyors, pipes, transport, or train systems | Must solve a defined transport problem and be maintainable |
| Exploration | Structures or destination content | Supplies discoveries and a coherent frontier loop; server-safe |
| Performance | Minimal compatible optimization set | Tested together; no speculative stacking of overlapping mods |

## Selection rules

1. Search for the exact Minecraft 1.21.1 NeoForge release, not merely a mod page that lists 1.21.
2. Verify dependencies and required library versions.
3. Check whether a dependency is client-only, server-only, or required on both sides.
4. Read release notes and known issues for the exact file.
5. Test a clean client launch, new world, save/reload, and dedicated-server join.
6. Add one logical group at a time and retain a known-good baseline.
7. Record the exact filename, version, source, dependency, and test result in the eventual manifest.
8. Do not include experimental addons in the critical path until they pass the same tests.

## Performance policy

The target machine is modest: Windows 11, Intel i7-9750H, GTX 1650 4 GB, and approximately 8 GB system memory. Keep the pack lean and aim to remain usable with around 4 GB allocated to Minecraft where feasible. This is a target to measure, not a guarantee.

Avoid:
- Multiple mods doing the same optimization job.
- Large optional content mods without a campaign role.
- Heavy worldgen stacks before measuring new-world generation.
- Client rendering features as mandatory server dependencies.
