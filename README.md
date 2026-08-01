# u1-motion-tweaks

[![licence](https://img.shields.io/badge/licence-AGPL--3.0-blue)](LICENSE)
[![release](https://img.shields.io/github/v/release/Bespok3d/u1-motion-tweaks)](https://github.com/Bespok3d/u1-motion-tweaks/releases)
![printer](https://img.shields.io/badge/printer-Snapmaker%20U1-informational)
![stock firmware](https://img.shields.io/badge/stock%20firmware-no%20flashing-brightgreen)

A co-repo of Bespok3d plugins for the Snapmaker U1 that publishes its own sub-list.

Plugins:

- **klipper-motion** - Cleaner surfaces and quieter moves, from the latest Klipper motion code.
- **tmc-autotune** - Argolein's optimized TMC2240 driver parameters for X/Y.
- **tmc-low-current** - Cooler, quieter X/Y motion at reduced stepper current.

Collections (`kind:collection`, no payload of their own, they install a set of plugins in one go):

- **performance-pack** - "Performance Pack": klipper-motion, tmc-autotune, tmc-low-current, and
  purge-line-back. `purge-line-back` ships from the `u1-klipper-config-enhancers` repo; a collection
  may name a member published by another repo.

## Layout

```text
u1-motion-tweaks/
  <plugin-id>/          # one plugin = one dir; its name is the manifest .name
    manifest.json
    files/              # payload the daemon places on the printer
    doc/README.md       # rendered in-app; not deployed
  .github/workflows/release.yml
  index.json            # the published sub-list (committed; referenced by main-index lists[])
  dist/                 # build output (gitignored)
```

Each plugin declares WHAT (a destination `class` + a `restart` hook), never a path or a raw
command; the printer-side adapter realizes it.

## Build locally

Needs Node.js 20+. Builds run through the shared `Bespok3d/b3-builder` tool:

```sh
npm install github:Bespok3d/b3-builder
npx b3-builder build --source ./klipper-motion --atom-repo Bespok3d/u1-motion-teweaks
# -> dist/klipper-motion-<ver>.b3 + dist/klipper-motion.atom.json
```

Drop `--source` to build every plugin in the repo at once.

## Releasing

Bump a plugin's `manifest.json` `version` and push to `main`. CI runs the `Bespok3d/b3-builder`
Action over the whole repo, which packs each `.b3`, cuts a release per plugin, assembles this repo's
`index.json` sub-list as `U1 Motion Tweaks`, and registers it in `Bespok3d/main-index`
(`lists/<repo>.json`). Secrets: `MAIN_INDEX_TOKEN` (contents:write on main-index) and
`REGISTRY_SIGNING_KEY` (the org registry key the `b3-builder` Action signs each `.b3` and atom with).

## Composition

Bespok3d's own code in this repository is under the repository licence below. The works listed here
are separate works, aggregated with it, each under its own licence. They are not under the repository
licence.

| Component | Licence | Where its licence text is |
| --- | --- | --- |
| The eight Klipper motion patches shipped by `klipper-motion` | GPL-3.0-only | [vendor/klipper-motion-patches/](vendor/klipper-motion-patches/) |
| The reduced current fragment shipped by `tmc-low-current` | GPL-3.0-only | [vendor/tmc-current-tweak/](vendor/tmc-current-tweak/) |

Both ship at their package path under `<plugin>/files` rather than under `vendor/`, because that is
the fixed package payload root; each `vendor/` directory records where its files are and what, if
anything, Bespok3d changed in them.

The `tmc-autotune` config carries 38 TMC2240 parameter values that are not Bespok3d's. They reached
the U1 through the Extended Firmware overlay `32-feature-klipper-tweaks`, whose own file header names
Argolein's SnapmakerU1-CustomConfig as their origin. That repository declares no licence, so nothing
of theirs is copied: the file that carries the values was written by the Bespok3d project against the
register field names Klipper documents, and that file alone is under the repository licence. Its
`doc/ATTRIBUTIONS.md` records the evidence for every part of this.

## Licence

Copyright (C) 2026 unlucio and the Bespok3d contributors

This program is free software: you can redistribute it and/or modify it under the terms of the GNU
Affero General Public License as published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without
even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU Affero
General Public License for more details.

You should have received a copy of the GNU Affero General Public License along with this program. If
not, see <https://www.gnu.org/licenses/>. The full text is in [LICENSE](LICENSE).

Bespok3d is a project of the Bespok3d Organisation, which is not a legal entity. Copyright is held by
the individual authors named above.

This licence covers Bespok3d's own code. It does not cover the separate works listed under
Composition, which keep their own licences.

## Maintainership

These plugins are published and maintained by the Bespok3d org, and several of them repackage or
build on upstream source material. If you own the source material a plugin is based on and would
rather manage it yourself, you are welcome to contact the org to claim it back. The one condition is
that it stays actively maintained: a claimed plugin left to rot will be reclaimed so users are never
stranded on an abandoned package.

## Support this project

`tmc-autotune` and `performance-pack` are Bespok3d's own work. `klipper-motion` and `tmc-low-current`
package software written by other people, and a donation here is not a donation to them.

If our part saved you an afternoon, you can [buy me a coffee](https://buymeacoffee.com/unlucio).
