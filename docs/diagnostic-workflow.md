# MERIDIAN diagnostic workflow

## Baseline capture
Before changing the mod list:
1. Duplicate the working 0.1.0 instance and world.
2. Record launcher, Minecraft, NeoForge, Java and JVM arguments.
3. Record idle title-screen RAM, in-world RAM after 5 minutes, average FPS and 1% lows if available.
4. Record world load time and time to join/rejoin.
5. Keep `latest.log`, `debug.log` (if generated), and crash reports.

## Crash investigation
1. Reproduce once on a copy of the instance/world.
2. Preserve the complete crash report and logs before changing anything.
3. Identify the first meaningful exception and the earliest mod-owned stack frame; do not assume the last mod mentioned caused the crash.
4. Compare against the previous known-good build.
5. Disable or update one suspected component at a time.
6. Re-test the original reproduction steps.

Not Enough Crashes is supplementary. It does not replace the original crash report or log.

## Performance investigation
### Client-side
- Record FPS, frame-time spikes, render distance, simulation distance, resolution and shader state.
- Compare the same location and camera direction.
- Use `/sparkc profiler` for a client profile where supported; stop with `/sparkc profiler --stop`.

### Server / integrated-server
- Record TPS/MSPT and player count.
- Use `/spark profiler` for a server profile; stop with `/spark profiler --stop`.
- Use Observable as a second view when investigating expensive block entities, after its NeoForge compatibility is validated.

### Memory
- Record allocated heap, used heap, GC behavior and whether memory climbs continuously after repeated exploration/world loading.
- Do not diagnose a memory leak from one high heap reading; Java may retain committed heap for reuse.
- Compare equivalent play sessions and let the game settle after loading.

## MERIDIAN factory stress test
Build a repeatable test area containing:
- IE power generation and distribution.
- Mekanism processing line with representative machines.
- Item/fluid transport.
- A moderate number of chests, cables, pipes and block entities.
- A repeatable input/output workload.

Capture a Spark profile while idle, then while the line is operating. This gives us a baseline for future progression and automation additions.

## Report bundle
When asking for help, include:
- `latest.log`
- `debug.log` if present
- crash report if present
- Spark profile link for performance problems
- exact reproduction steps
- whether the problem occurs in a fresh test world or only the established save
- the last known-good mod list/build
