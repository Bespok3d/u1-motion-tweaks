# Performance Pack

Quieter, cooler X/Y motion and a purge line that does not sit in front of your part.

## What it installs

| Plugin | What it does |
| --- | --- |
| TMC Auto-Tuned | Argolein's optimized TMC2240 driver settings for the X and Y steppers (StealthChop tuning, CoolStep, hysteresis) |
| TMC Low Current | Lowers the X and Y run current from 1.2 to 1.0 A, for less heat and less noise |
| Purge Line at Back | Moves the start-of-print purge line from the front of the plate to the back, for all four tools |

All three install together with a single service restart.

The two driver plugins set different things (one sets the driver registers, the other sets the run
current), so they compose instead of fighting.

## Read this before you install

These are low-level stepper driver changes on a stock printer.

- **Watch the motor temperatures on your first print.** Different driver settings change how much
  heat the motors make.
- **A layer shift means the current is too low for that move.** Heavy or fast moves at 1.0 A can skip
  steps. Remove TMC Low Current and the stock 1.2 A comes back; the rest of the pack stays.
- **Snapmaker U1 only.** The settings are for the U1's TMC2240 drivers on X and Y.

## After installing

Nothing to configure. The purge line prints at the back from the next print on, and the motion is
audibly quieter.
