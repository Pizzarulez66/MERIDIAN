# Known risks and decisions

- **Renderer compatibility:** Sodium is the selected renderer candidate. Do not include Embeddium simultaneously. Validate shader support only if shaders become a project requirement.
- **Culling edge cases:** Entity Culling can cause issues with some animated or modded entities. Test IE multiblocks, Mekanism machine visuals, particles and entity animations.
- **Observable metadata:** The project advertises NeoForge compatibility, but dependency metadata and the exact 1.21.1 artifact must be checked before inclusion. Do not assume Forge dependencies apply identically to NeoForge.
- **Lithium:** Do not add until a specific 1.21.1 NeoForge file is confirmed and tested with the pinned core mods.
- **C2ME:** Deferred because world-generation threading can conflict with mods that hook worldgen.
- **Low RAM:** A profiler or extra diagnostic mod has a small cost. Keep the always-on set lean; optional diagnostics may be removed from the player-facing release if they add meaningful overhead.
- **Version pinning:** A compatibility badge is not a compatibility test. The full modpack is the final authority.
