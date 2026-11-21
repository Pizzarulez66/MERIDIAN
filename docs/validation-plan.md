# Validation Plan

A feature is not complete because it appears in a quest description or works once in a developer world. It must be reproducible.

## Platform and boot
- [ ] Exact Minecraft 1.21.1 and NeoForge build recorded.
- [ ] Exact Java runtime requirement recorded.
- [ ] Clean client launches without errors.
- [ ] Clean dedicated server starts without errors.
- [ ] New world generates and can be entered.
- [ ] World saves, exits, and reloads.
- [ ] Two clients can join and play together.
- [ ] No missing or mismatched registry entries.

## Core mod integration
- [ ] Mekanism machines place, configure, process, and persist correctly.
- [ ] Immersive Engineering multiblocks form and persist correctly.
- [ ] Power transfer works as documented.
- [ ] Item, fluid, and gas transfer works for intended routes.
- [ ] Recipe changes are visible in the selected recipe viewer.
- [ ] No duplicate, dead-end, or bypass recipes.
- [ ] Cross-mod chains work on a dedicated server.

## Progression and quests
- [ ] Each milestone has clear prerequisites.
- [ ] Item submission objectives count correctly.
- [ ] Recipe objectives trigger correctly.
- [ ] Unlocks synchronize to all players as intended.
- [ ] Quest progress persists after restart.
- [ ] Optional objectives are clearly marked.
- [ ] Player-certified construction checks are described honestly.
- [ ] No arbitrary machine-inspection or throughput claims.

## Meridian Core and Gate
- [ ] Each of the five component families has a discoverable production path.
- [ ] Bulk materials have sustainable supply routes.
- [ ] Rare exploration rewards have bounded/understandable sources.
- [ ] Core crafting cannot be accidentally bypassed.
- [ ] Gate construction requirements are clear.
- [ ] Activation is server-authoritative.
- [ ] Gate state persists after restart.
- [ ] Multiple players can use the Gate correctly.
- [ ] Failed activation does not consume critical items without clear feedback.
- [ ] Destination arrival and return path are tested.

## Performance
- [ ] Startup time recorded.
- [ ] Idle memory recorded.
- [ ] Memory during representative factory operation recorded.
- [ ] Chunk/worldgen performance checked.
- [ ] Large IE multiblocks and Mekanism factories tested together.
- [ ] Client rendering and server tick performance checked separately.
- [ ] No overlapping optimization mods without measured benefit.
- [ ] Target allocation remains practical on an 8 GB system.

## Release gate

A release candidate must:
1. Pass all critical boot, save, server, progression, and Gate tests.
2. Have a complete version-locked mod manifest.
3. Include reproducible installation instructions.
4. Document known issues and deferred features.
5. Be tested from a clean install, not only a long-lived development instance.
