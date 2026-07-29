# Attributions - tmc-autotune

**Plugin author:** the TMC2240 driver parameter values are not Bespok3d's; the file that carries them
was written by Bespok3d

Retunes the stepper drivers for quieter, cooler running.

| Upstream project | Author | Licence | Needed at runtime | What of theirs ships in this package |
| --- | --- | --- | --- | --- |
| Extended Firmware overlay `32-feature-klipper-tweaks`, file `tweaks/klipper/tmc_autotune.cfg` | paxx12 | GPL-3.0-only | no | nothing: no line of that file is copied |
| SnapmakerU1 CustomConfig `01_ArgoConfig.cfg`, which that overlay file names as the origin of the values | Argolein | none declared | yes | the 38 driver parameter values, unchanged |

## Where the values come from, and how that was established

The values reached the U1 community through the Extended Firmware overlay
`32-feature-klipper-tweaks`, file `tweaks/klipper/tmc_autotune.cfg`, added by paxx12 on 2026-02-01
(commit `55786fb`, "firmware-config: add klipper TMC driver tweaks"). That file's own header records
their origin as
https://github.com/Argolein/SnapmakerU1/blob/main/SnapmakerU1-CustomConfig/01_ArgoConfig.cfg. That
header line is the whole basis for crediting Argolein; the Bespok3d project has not inspected
Argolein's repository contents.

The Argolein repository declares no licence: GitHub reports no licence for it and its licence
endpoint returns 404, checked 2026-07-28. No permission to copy anything of theirs can therefore be
assumed, so nothing of theirs is copied.

The 38 `driver_` values this package installs are the same values the overlay file sets, unchanged.
They are reproduced because they are what this tuning is: different values would be a different
plugin.

## What Bespok3d wrote

The file that carries them was written by the Bespok3d project on 2026-07-28, against the TMC2240
register field names as Klipper documents them in its Configuration Reference under `[tmc2240]`. Its
wording, its comments, its ordering and its grouping are Bespok3d's own and are under this
repository's licence. No line of the overlay file is copied into it. Earlier releases of this plugin
shipped the overlay file itself, byte for byte; this release does not.
