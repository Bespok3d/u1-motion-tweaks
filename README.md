# u1-motion-tweaks

A co-repo of Bespok3d plugins for the Snapmaker U1 that publishes its own sub-list.

Plugins:

- **klipper-motion** - Cleaner surfaces and quieter moves, from the latest Klipper motion code.
- **tmc-autotune** - Argolein's optimized TMC2240 driver parameters for X/Y.
- **tmc-low-current** - Cooler, quieter X/Y motion at reduced stepper current.

## Layout

```text
u1-motion-tweaks/
  <plugin-id>/          # one plugin = one dir; its name is the manifest .name
    manifest.json
    files/              # payload the daemon places on the printer
    doc/README.md       # rendered in-app; not deployed
  scripts/{pack.sh,generate-atom.mjs,assemble-list.mjs}
  .github/workflows/release.yml
  index.json            # the published sub-list (committed; referenced by main-index lists[])
  dist/                 # build output (gitignored)
```

Each plugin declares WHAT (a destination `class` + a `restart` hook), never a path or a raw
command; the printer-side adapter realizes it. See `Bespok3d/doc/anatomy-of-a-plugin.md`.

## Build locally

```sh
sh scripts/pack.sh                            # -> dist/<name>-<ver>.b3 per plugin
node scripts/generate-atom.mjs --plugin <id>  # -> dist/<id>.atom.json
node scripts/assemble-list.mjs                # -> index.json from dist/*.atom.json
```

## Releasing

Bump a plugin's `manifest.json` `version` and push to `main`. CI packs each `.b3`, cuts a release
per plugin, regenerates this repo's `index.json` sub-list, and registers it in `Bespok3d/main-index`
(`lists/<repo>.json`). Secret: `MAIN_INDEX_TOKEN` (contents:write on main-index). Signing deferred.
