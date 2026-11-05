# Changelog

## 0.2.1 - 2026-11-05

- Asks for Smoother Motion 0.1.5 or newer, the version that installs the three U1 Base Layer motion
  plugins instead of patching the printer's files itself. The older one fails on Snapmaker firmware
  2.1 and undoes the base layer's motion patches.

## 0.2.0 - 2026-08-01

- Added Smoother Motion (`klipper-motion`) to the pack, so the collection now updates the motion
  engine itself as well as the driver settings and the purge line.

## 0.1.0 - 2026-07-27

- First release of the "Performance Pack" collection: installs TMC Auto-Tuned, TMC Low Current, and
  Purge Line at Back together, in one batch with a single service restart.
