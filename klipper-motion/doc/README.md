# Klipper Motion Backports

Backports several upstream Klipper motion improvements to the U1's Klipper, for smoother
moves and better input-shaper tuning.

> **Version-sensitive.** This patches Klipper source files. It targets a specific Klipper
> version; if your Klipper differs, the plugin may not apply cleanly.

## What it brings

- **Sweeping-vibrations** resonance test and `accel_per_hz` for input-shaper calibration.
- Junction-deviation / centripetal cornering for smoother direction changes.
- A tuned lookahead flush time for more consistent motion planning.

## Using it

Install the plugin; Klipper restarts and the new behavior is active. Use the standard
resonance-testing and input-shaper workflow (`TEST_RESONANCES`, `SHAPER_CALIBRATE`).

## Notes

- Patches `/home/lava/klipper/klippy/...`; reverted on uninstall and re-applied after an OTA
  firmware update.
- Snapmaker U1. Not yet verified on every firmware revision.
