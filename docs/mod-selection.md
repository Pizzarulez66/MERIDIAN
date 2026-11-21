# Mod Selection and Compatibility Policy

## Status vocabulary

- **Core:** Required to express the pack's identity.
- **Candidate:** Promising, but not yet validated for the exact target.
- **Optional:** Adds a useful route or convenience but is not required for the main campaign.
- **Deferred:** Intentionally postponed until the foundation works.
- **Rejected:** Tested or reviewed and excluded, with a recorded reason.

Nothing below should be treated as a final version lock unless it appears in the manifest with a passing test result.

## Core pillars

| Mod | Status | Intended responsibility |
|---|---|---|
| Mekanism 10.7.19.85 | Candidate core baseline | Advanced ore processing, chemical systems, factories, materials, and utilities |
| Immersive Engineering 12.4.2-194 | Candidate core baseline | Coke/steel, heavy fabrication, multiblocks, visible infrastructure, and material handling |

See `pack/manifest/core-baseline.md` for exact filenames and release references.

## Support categories to evaluate

| Category | Candidate direction | Acceptance criteria |
|---|---|---|
| Quests | FTB Quests ecosystem | Correct 1.21.1 NeoForge builds; all required libraries identified; multiplayer sync tested |
| Custom content | Dedicated `meridian` NeoForge mod | Stable registry IDs, server-authoritative behavior, save/reload and dedicated-server tests |
| Data changes | Vanilla datapacks | Use only for features datapacks can actually express |
| IE expansion | Immersive Petroleum or other IE addons | Exact 1.21.1 NeoForge release; adds a useful industrial role without bloating progression |
| Mekanism expansion | Official/compatible Mekanism addons | Exact version and dependency chain; no duplicate or obsolete progression |
| Storage | AE2 or a lighter alternative | Optional convenience; must not erase logistics gameplay or exceed performance budget |
| Logistics | Existing IE/Mekanism transport first | Add another transport mod only when a demonstrated gap exists |
| Exploration | Structures or destination content | Supplies discoveries and a coherent frontier loop; server-safe |
| Performance | Minimal compatible optimization set | Tested together; no speculative stacking of overlapping mods |

## Scripting policy

MERIDIAN will **not** use KubeJS or CraftTweaker. Prefer:
1. Vanilla datapacks for recipes, tags, loot, advancements, and other supported data-driven changes.
2. A dedicated `meridian` NeoForge mod for custom registered items, blocks, interactions, persistent state, networking, and mechanics that datapacks cannot provide.

Do not add a scripting framework simply because it is a common modpack convention.

## Selection rules

1. Search for the exact Minecraft 1.21.1 NeoForge release, not merely a mod page that lists 1.21.
2. Verify dependencies and required library versions.
3. Check whether a dependency is client-only, server-only, or required on both sides.
4. Read release notes and known issues for the exact file.
5. Test a clean client launch, new world, save/reload, and dedicated-server join.
6. Add one logical group at a time and retain a known-good baseline.
7. Record exact filename, version, source, side, dependencies, and test result in the manifest.
8. Do not include experimental addons in the critical path until they pass the same tests.

## Performance policy

The target machine is modest: Windows 11, Intel i7-9750H, GTX 1650 4 GB, and approximately 8 GB system memory. Keep the pack lean and aim to remain usable with around 4 GB allocated to Minecraft where feasible. This is a target to measure, not a guarantee.

Avoid:
- Multiple mods doing the same optimization job.
- Large optional content mods without a campaign role.
- Heavy worldgen stacks before measuring new-world generation.
- Client rendering features as mandatory server dependencies.
