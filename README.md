# Ender-3 S1 / Klipper print failure cheat sheet (free, first 10 of 30)

Symptom, most likely cause, fastest fix for a stock bed-slinger with a weak 4010 part fan, PLA, and Klipper.

| # | Symptom | Most likely cause | Fast fix |
|---|---|---|---|
| 1 | First layer: round separated lines, corners lifting, part skates | Z-offset too high OR bare glass no adhesion promoter | Babystep Z -0.02..-0.06; glue stick; bed 60->65 |
| 2 | Elephant foot: bottom 1-3 layers bulge wider | First layer over-squished + bed 60 holding base molten | Z +0.03..+0.05; bed -5; EFC 0.1-0.2 mm |
| 3 | Warp / corner lift: base curls off glass | Glass cooled at unclamped rear + no brim + draft | Brim 5-8 mm; kill draft; glue |
| 4 | Layer shift: clean step, all layers above offset | Y belt/pulley slip or missed Y steps from accel 5000 + heavy glass; or `Timer too close` | max_accel 2000; can't un-shift |
| 5 | Z banding: horizontal bands at regular Z pitch | Bent/dry Z leadscrew, binding nut, or inconsistent layer time | Lube leadscrew; check coupler; constant layer time |
| 6 | Ghosting: echo of corners downstream | Stale input shaper + accel 5000 + loose belts | Re-run SHAPER_CALIBRATE; drop accel; tension belts |
| 7 | Under-extrusion: thin/missing lines, worsens over time | Partial clog / heat creep (weak 4010, long prints) -> starvation | Cold pull; check both fans; -5 C; slow to 40 |
| 8 | Over-extrusion: blobby oversized walls, raked top | extrude_factor >1, over-set flow, filament dia mis-set | M221 S95; flow 0.94-0.96; verify 1.75 dia |
| 9 | Stringing / oozing | Wet PLA first; then temp too high; then travel/retract | Dry 4 h @ 45-50; drop to 205; combing/wipe |
| 10 | Blobs / zits / seam scars | PA / retract mismatch at seam; Z-hop restart ooze | Tune PA +-0.005; wipe; seam = sharpest/random |

## Get all 30 + checklist

The full **3D Print Failure Fixer** PDF has all 30 failures, a pre-flight checklist and the calibration order: https://spectre5.gumroad.com/l/kdocpp ($5).

More guides: https://patreon.com/123black
