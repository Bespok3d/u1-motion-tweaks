# Klipper motion patches

A separate work, aggregated with this repository. Not covered by this repository's licence.

| | |
| --- | --- |
| Upstream | <https://github.com/Klipper3d/klipper> |
| Copyright | Kevin O'Connor and the Klipper contributors |
| Also from | the Snapmaker U1 Extended Firmware overlay `11-patch-klipper`, <https://github.com/paxx12/SnapmakerU1-Extended-Firmware> |
| Licence text retrieved | 2026-07-28 |
| Licence | GPL-3.0-only, in [LICENSE](LICENSE) |

## What it is

Eight patches that the `klipper-motion` plugin applies to the Klipper source on the printer. What
they carry is upstream Klipper: commits by Kevin O'Connor, MRX8024 and Dmitry Butyugin, plus one
Snapmaker specific fixup written by paxx12 for the overlay named above.

## Where the files are

The patches ship to the printer, so they live at their package path rather than in this directory:

```text
klipper-motion/files/patches/
```

The package payload root is fixed at `<plugin>/files`, so a patch stored under `vendor/` would not
reach the printer. This directory carries the licence text and this provenance note.

## Modification notice

GPLv3 section 5(a) requires a modified work to carry prominent notices stating that it was modified
and the date. Five of the eight patches ship byte for byte as they came from the overlay. The other
three, `04a_resonance_sweeping.patch`, `04b_shaper_calibrate.patch` and
`04c_toolhead_junction_v2.patch`, are the overlay's single `04_16b4b6b30.patch` split by the Bespok3d
project, in this repository's first commit on 2026-06-05, into one file per patched file, so the
daemon can apply and roll them back individually. Each of the three keeps the original `From`, author and `Subject` header of Dmitry
Butyugin's upstream commit, and the hunks inside them are unchanged.
