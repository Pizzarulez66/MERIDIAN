# Development Workflow

## Working rules

- Keep changes small enough to test and review.
- Never silently change the Minecraft or loader target.
- Record exact mod versions and download sources in the manifest once selected.
- Do not commit untested scripts as if they were production-ready.
- Keep a known-good pack backup before changing dependencies.
- Prefer reproducible steps over undocumented manual edits.
- Treat client and dedicated-server behavior as separate test targets.

## Definition of done

A feature is done only when:
1. Its purpose and progression role are documented.
2. Dependencies and exact versions are recorded.
3. It works in a clean development instance.
4. It works on a dedicated server where applicable.
5. Save/reload and multiplayer behavior are tested.
6. It has no unintended progression bypass.
7. Performance impact is understood.
8. User-facing quest text explains what to do and why.

## Suggested first implementation tasks

1. Verify the exact 1.21.1 NeoForge builds for Mekanism and Immersive Engineering.
2. Launch a minimal instance with only their required dependencies.
3. Add a recipe viewer and confirm all core recipes are discoverable.
4. Prototype one IE-to-Mekanism material chain.
5. Prototype one Mekanism-to-IE or shared-infrastructure chain.
6. Measure memory use before selecting optional content.
7. Choose the quest system and create a tiny test chapter before writing the full campaign.
