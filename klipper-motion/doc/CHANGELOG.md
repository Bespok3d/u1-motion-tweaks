# Changelog

## 0.1.5 - 2026-11-05

- The first release of Smoother Motion as a set of three U1 Base Layer plugins to reach the store.
  0.1.4 made that change but was never published, so the store kept offering 0.1.3, which patches
  the printer's files itself. On Snapmaker firmware 2.1 that version fails to install and undoes the
  U1 Base toolhead and shaper calibrate patches. Updating from 0.1.3 removes it and puts the three
  base plugins on instead.
- Asks for U1 Base resonance tester 0.1.1 or newer, the first that fits firmware 2.1. It brings
  U1 Base toolhead and U1 Base shaper calibrate with it.

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
