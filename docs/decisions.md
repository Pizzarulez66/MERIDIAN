# Decision Log

This document distinguishes current decisions from ideas that still need evidence.

## Accepted direction

### D-001 — Core identity is Mekanism × Immersive Engineering
**Status:** Accepted

Both mods are mandatory pillars and must contribute throughout the progression. Other mods exist to support this identity, not replace it.

### D-002 — The main trophy is the Meridian Core
**Status:** Accepted as a design direction

The Core is a multi-stage crafted artifact made from five component families: Industrial Heart, Chemical Matrix, Power Singularity, Control Lattice, and Astral Keystone. Exact recipes remain open.

### D-003 — The Gate is the actual campaign finale
**Status:** Accepted as a design direction

Crafting the Core is not sufficient to finish the main story. The player must construct and commission the Meridian Gate.

### D-004 — Post-game is optional
**Status:** Accepted

Frontier outposts, inter-world logistics, and second-generation systems are additional goals, not mandatory barriers to the main ending.

### D-005 — No fake automation verification
**Status:** Accepted

Quest objectives must not claim to inspect arbitrary builds or measure production unless a tested implementation can do so.

### D-006 — Target platform
**Status:** Provisional lock

Minecraft 1.21.1 NeoForge. Exact NeoForge build, Java runtime, and mod versions must be verified before locking.

## Open decisions

### O-001 — Gate destination
**Options:** Existing dimension; custom Gate with existing destination; dedicated custom dimension.  
**Current lean:** Prototype custom Gate mechanics first; defer custom dimension decision until the core pack is stable.

### O-002 — Script engine
**Question:** Which exact 1.21.1 NeoForge scripting engine and integrations provide stable server-side recipe, item, and progression support?  
**Rule:** Do not lock based on a different Minecraft version or loader.

### O-003 — Quest system
**Question:** Which quest stack is stable on the selected platform and supports the campaign requirements without unnecessary dependencies?

### O-004 — Custom mod scope
**Question:** Can the Gate activation and Core content be implemented safely with existing mods/scripts, or does the project need a small dedicated `meridian` mod?

### O-005 — Optional storage and transport
**Question:** Which systems add useful player choice without trivializing logistics or exceeding the performance budget?

### O-006 — Exploration content
**Question:** Which structure/worldgen additions support the Astral Keystone and frontier mystery while remaining lightweight and server-safe?

## Change policy

When an open decision is resolved, record:
- The chosen option.
- Evidence or test performed.
- Exact versions/files if applicable.
- Known trade-offs.
- Date and any follow-up work.
