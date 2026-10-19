# Signathing evidence log (public mirror)

A copy of the [Signathing](https://signathing.com) evidence chain that lives outside Signathing's servers.

Every signing event on Signathing (sent, opened, signed, declined, completed, voided) is appended to one public hash chain. Each entry commits to the private details of the event through a hash without publishing them; the public entry is only `seq, at, type, fingerprint, detail_hash, prev_hash, hash`. Each finished UTC day is sealed with the hash of its last entry, the day's page is archived by the Internet Archive, and the same day is committed here. Two parties Signathing cannot quietly edit now hold a copy: the Internet Archive and GitHub's commit history.

- `days/YYYY-MM-DD.json`: the seal (first and last seq, head hash, archive link) and every public entry of that day.
- `latest.json`: the live chain head at the last publish.
- `HEADS.md`: table of sealed days.

## Check it

```
hash = sha256(prev_hash + "\n" + seq + "\n" + at + "\n" + type + "\n" + fingerprint + "\n" + detail_hash)
```

Entry 1 has 64 zeros as `prev_hash`. Recompute every entry in a day file and compare the last one to `seal.head_hash`; compare that to the Internet Archive snapshot and to https://signathing.com/api/evidence/days. If you hold a signed document, its sender can export an evidence package that carries the private preimages; the open verifier at https://signathing.com/verifier/verify-signathing.mjs checks the package against this chain.

Commits are made by an automated publisher on Signathing's server once a day. Nothing here is ever rewritten; if a commit were force-pushed away, the Internet Archive copy and anyone who cloned this repository would show it.

Live log and explanation: https://signathing.com/transparency
