# Klipper Motion Backports

Backports several upstream Klipper motion improvements to the U1's Klipper, for smoother
moves and better input-shaper tuning.

> **Version-sensitive.** The U1 Base Layer plugins this one asks for patch Klipper source files on
> the printer, one fragment per firmware generation. Their own pages list the firmware they fit;
> on firmware 2.1 U1 Base resonance tester needs to be 0.1.1 or newer.

## What it brings

- **Sweeping-vibrations** resonance test and `accel_per_hz` for input-shaper calibration.
- Junction-deviation / centripetal cornering for smoother direction changes.
- A tuned lookahead flush time for more consistent motion planning.

## Using it

Install the plugin; the three U1 Base Layer motion plugins it asks for come with it, Klipper
restarts and the new behavior is active. Use the standard
resonance-testing and input-shaper workflow (`TEST_RESONANCES`, `SHAPER_CALIBRATE`).

## Notes

- Patches `/home/lava/klipper/klippy/...`; reverted on uninstall and re-applied after an OTA
  firmware update.
- Snapmaker U1. Installed and running; not re-checked against every firmware revision.
