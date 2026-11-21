# Server scripts

Put server-side recipe and progression scripts in this directory.

Suggested split once the instance has passed the compatibility tests:

- `10_ie_to_mekanism.js` — IE outputs that become Mekanism processing inputs.
- `20_mekanism_to_ie.js` — Mekanism outputs that become IE fabrication inputs.
- `30_meridian_components.js` — late-game Grid Synchronizer and project components.
- `90_balance_overrides.js` — deliberate recipe removals/overrides, kept separate from integration additions.

Use `ServerEvents.recipes(event => { ... })`. Mekanism recipe builders are documented under `event.recipes.mekanism` by KubeJS Mekanism. IE machine recipe methods depend on the tested Immersive Engineering JS build or IE's native datapack recipe schema.

**Important:** do not paste guessed item IDs into production scripts. Confirm each registry ID in JEI/EMI or the loaded registry, test the recipe in its target machine, and verify the recipe survives a dedicated-server restart.
