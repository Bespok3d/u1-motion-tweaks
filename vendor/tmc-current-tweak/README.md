# TMC reduced current tweak

A separate work, aggregated with this repository. Not covered by this repository's licence.

| | |
| --- | --- |
| Upstream | <https://github.com/paxx12/SnapmakerU1-Extended-Firmware> |
| Copyright | the Extended Firmware contributors |
| Origin | the `32-feature-klipper-tweaks` overlay, file `tmc_current.cfg`, TMC driver work credited upstream to @Argolein |
| Licence text retrieved | 2026-07-28 |
| Licence | GPL-3.0-only, in [LICENSE](LICENSE) |

## What it is

The Klipper config fragment that lowers the X and Y stepper run current. The `tmc-low-current` plugin
places it on the printer.

## Where the file is

The fragment ships to the printer, so it lives at its package path rather than in this directory:

```text
tmc-low-current/files/cfg/klipper/tmc-low-current.cfg
```

The package payload root is fixed at `<plugin>/files`, so a file stored under `vendor/` would not
reach the printer. This directory carries the licence text and this provenance note.

## Modification notice

None is owed. The fragment ships byte for byte as it came from the overlay, comments included. The
Bespok3d project changed nothing in it, only the file name.
