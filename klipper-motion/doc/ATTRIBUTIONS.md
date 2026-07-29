# Attributions - klipper-motion

**Plugin author:** Kevin O'Connor, MRX8024 and Dmitry Butyugin (upstream Klipper commits) and paxx12 (Extended Firmware overlay `11-patch-klipper`), packaged by Bespok3d

Upstream Klipper motion fixes the stock firmware predates.

| Upstream project | Author | Licence | Needed at runtime | Code ships in this package |
| --- | --- | --- | --- | --- |
| Klipper | Kevin O'Connor and the Klipper contributors | GPL-3.0 | yes | yes |
| resonance_tester chip selection and accel_per_hz | MRX8024 | GPL-3.0 | yes | yes |
| resonance_tester sweeping vibrations test | Dmitry Butyugin | GPL-3.0 | yes | yes |
| Extended Firmware overlay `11-patch-klipper` | paxx12 | GPL-3.0 | no | yes |

This plugin ships eight patches, applied to the Klipper source on the printer. All eight come from
the Extended Firmware overlay `11-patch-klipper`, GPL-3.0-only, and stay under that licence; the
licence text and the provenance note are in `vendor/klipper-motion-patches/` at the root of this
repository. Five of them ship unchanged, byte for byte, keeping their original author and commit
message. The other three are that overlay's `04_16b4b6b30.patch` split into one file per patched
file; each keeps the original header naming Dmitry Butyugin, whose upstream Klipper commit it is, and
the hunks inside them are unchanged.

What the patches carry is upstream Klipper: commits by Kevin O'Connor, MRX8024 and Dmitry Butyugin.
That overlay also carries commits by jimmyjon711. Upstream: https://github.com/Klipper3d/klipper

The last patch, the Snapmaker-specific fixup, was written by paxx12 for that overlay.
