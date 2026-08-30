# Changelog

## 0.1.4 - 2026-08-24

- The motion updates now come from the U1 Base Layer, which installs with this plugin. Nothing about
  your printer changes: the same updates are applied, and another plugin that needs the same files
  can now be installed alongside this one instead of clashing with it.

## 0.1.3

- Declares its licence, GPL-3.0-only, the licence Klipper grants for the code these patches change.
- The three patches split out of a single upstream commit now carry that commit's author, date and
  subject again, plus a line recording the split. No patched code changed.

## 0.1.2

- Publishing from bundled to online official registry.
- Backports upstream Klipper motion improvements to the U1: sweeping-vibrations
  resonance test, accel_per_hz, junction-deviation cornering, and a tuned
  lookahead flush time.
