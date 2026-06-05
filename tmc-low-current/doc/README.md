# TMC Reduced Current

Lowers the X and Y stepper run current from 1.2 A to 1.0 A for quieter, cooler motors.

> **Experimental.** This changes low-level driver current. Watch print quality after
> enabling.

## What it does

- Sets X and Y motor run current to 1.0 A.
- Lowers motor heat generation.
- Makes the motors noticeably quieter.

## Risks

- Skipped steps under heavy load or fast moves.
- Possible layer shifts on demanding prints.
- Reduced positioning accuracy under high acceleration.

## Recommendation

- Watch for layer shifts or positioning issues after enabling.
- Uninstall if you hit motion problems.

Klipper restarts when this plugin is installed or removed; no full reboot needed. Snapmaker
U1 only. Do not run this together with a conflicting current tweak.
