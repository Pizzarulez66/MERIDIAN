# Implementation validation checklist

Before recipe implementation:
- [ ] Confirm Minecraft 1.21.1 and NeoForge 21.1.249.
- [ ] Confirm Mekanism 10.7.19.85 and Immersive Engineering 12.4.2-194.
- [ ] Inspect recipe serializer IDs and item IDs in the installed JARs.
- [ ] Check tags and ingredient alternatives.
- [ ] Confirm datapack folder structure and pack format for 1.21.1.
- [ ] Implement only verified recipes.

After implementation:
- [ ] Load the datapack in a fresh test world.
- [ ] Check startup and reload logs for recipe errors.
- [ ] Verify recipes in JEI.
- [ ] Test output and automation.
- [ ] Test recipe interactions with existing core mod recipes.
- [ ] Re-test in a duplicate of the baseline world.
- [ ] Save logs and recipe files alongside the development artifact.
