# Sealed days

Head hash of each sealed UTC day of the Signathing evidence chain. Recompute from the files in `days/` or from https://signathing.com/api/evidence/log. The `.ots` file next to each day is an OpenTimestamps proof of the head hash; `ots verify` it against the hash bytes once it names a Bitcoin block. The X column is the same head posted from @Signathing.

| Day | Seq | Entries | Head hash | Internet Archive | Bitcoin (OpenTimestamps) | X |
| --- | --- | --- | --- | --- | --- | --- |
| 2026-10-20 | 522 to 537 | 16 | `2eecc7217d6811ca500b79a1af9fbd072872aad001d2390b15daf991b98b26e1` | [snapshot](https://web.archive.org/web/20261021000005/https://signathing.com/transparency/2026-10-20) | [pending](days/2026-10-20.ots) | none |
| 2026-10-19 | 510 to 521 | 12 | `7fe40407e59422195723737f715958e44118b1b5872174887bf0ad75c7cf5c83` | [snapshot](https://web.archive.org/web/20261020000006/https://signathing.com/transparency/2026-10-19) | [block 972354](days/2026-10-19.ots) | none |
| 2026-10-18 | 1 to 509 | 509 | `dfd6ee711229ff8a465b65dd8f07844f9b4d2390cdd477ccbe9618707b17cad1` | [snapshot](https://web.archive.org/web/20261019000102/https://signathing.com/transparency/2026-10-18) | [block 972354](days/2026-10-18.ots) | none |
