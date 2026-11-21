# MERIDIAN Core Baseline — 2026-11-21

**Status:** Candidate baseline; not yet runtime-validated.

This records researched release candidates. It does not claim that the pack has booted successfully.

## Platform

| Component | Selection | Status |
|---|---|---|
| Minecraft | 1.21.1 | Fixed project target |
| Loader | NeoForge 1.21.1 line | Exact build still to be tested and pinned |
| Java | Java 21 | Baseline runtime for Minecraft 1.21.1 |
| Distribution | Client and dedicated server | Both core mods declare client/server support |

## Core mods

| Mod | Candidate version | Exact file | Status |
|---|---:|---|---|
| Mekanism | 10.7.19.85 | `Mekanism-1.21.1-10.7.19.85.jar` | Release; 1.21.1 NeoForge |
| Immersive Engineering | 12.4.2-194 | `ImmersiveEngineering-1.21.1-12.4.2-194.jar` | Release; 1.21.1 NeoForge |

### Release references

- Mekanism release page: https://modrinth.com/mod/mekanism/version/10.7.19.85
- Immersive Engineering release page: https://modrinth.com/mod/immersiveengineering/version/12.4.2-194
- Mekanism CurseForge file: https://www.curseforge.com/minecraft/mc-mods/mekanism/files/7904058
- Immersive Engineering files: https://www.curseforge.com/minecraft/mc-mods/immersive-engineering/files/all

## Compatibility notes

- Both selected files explicitly declare Minecraft 1.21.1, NeoForge, and client/server support.
- Immersive Engineering 12.4.2-194 is reported to require NeoForge 21.1.164 or newer. Confirm this against the actual jar metadata/startup log.
- The rendered Mekanism release metadata does not expose a clear minimum NeoForge build. Do not infer one.
- Do not choose a loader build merely because it is newer. Pin one exact NeoForge 21.1.x build and test both mods together.
- Required libraries, if any, must be determined from the downloaded files' metadata and actual launch log. Do not add speculative libraries.

## Deliberately excluded from the first boot

The first baseline contains only NeoForge, Mekanism, Immersive Engineering, and dependencies that the actual files declare mandatory. No quest mod, recipe viewer, optimization bundle, worldgen, or addon is needed to prove the core baseline.

## Tooling decision

- **No KubeJS.**
- **No CraftTweaker.**
- Prefer vanilla datapacks for recipe, tag, loot, and advancement changes when they can express the required behavior.
- Use a small dedicated NeoForge mod, `meridian`, for registered items, custom blocks, server-authoritative interactions, and mechanics datapacks cannot implement.
- Add the quest system only after the core client and dedicated server boot reliably.

## Validation checklist

- [ ] Download the exact files listed above.
- [ ] Confirm the filenames and loader labels.
- [ ] Select Java 21 in the launcher and server.
- [ ] Pin an exact NeoForge 21.1.x build.
- [ ] Launch a clean client with only the core baseline.
- [ ] Create a new world, save, quit, and reload.
- [ ] Start a dedicated server with the same mod set.
- [ ] Join with a client and test IE multiblocks and Mekanism machines.
- [ ] Record startup logs, memory use, and dependency findings.
- [ ] Only after all checks pass, mark this baseline validated.
