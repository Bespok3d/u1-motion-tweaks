# TMC AutoTune

Applies tuned stepper-driver settings for the U1's TMC2240 drivers on the X and Y axes.

> **Experimental.** This changes low-level driver parameters that override the defaults.
> Enable it deliberately and watch your printer for the first few prints.

## What it does

- Tunes PWM settings for quieter motion.
- Configures StallGuard and CoolStep parameters.
- Adjusts timing for better heat management and performance.

## Risks

- Motors may run hotter; make sure cooling is adequate.
- Under heavy load you could see reduced torque or skipped steps.
- Incorrect settings can affect print quality.

## Recommendation

- Monitor motor temperatures on first use.
- Test with simple prints before production work.
- Uninstall if you see motion or quality problems.

Klipper restarts when this plugin is installed or removed; no full reboot needed. Snapmaker
U1 only.
