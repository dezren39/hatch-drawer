# hatch-drawer — the public chunk drawer

**Purpose.** This is the bulk/binary overflow shelf paired with
[dezren39/hatch](https://github.com/dezren39/hatch) — the "junk drawer" for
public-safe material that is too chunky, too binary, or too numerous for the
main repo's history, but still worth versioning and keeping one clone away.
Its private sibling is `dezren39/hatch-personal-drawer`, paired with
`dezren39/hatch-personal`.

Created 2026-10-21 from the chunk-drawer research
(`~/workspace/library-build/chunk-drawer/RESEARCH.md`, sizing from the
2026-10-21 full-home inventory).

## What's here

Paths mirror the home directory they came from. Per-file sizes and SHA-256
hashes are in [MANIFEST.md](MANIFEST.md).

| Path in repo | Source | What it is |
|---|---|---|
| `workspace/avatars/` | `~/workspace/avatars` | Avatar / profile media (webp, jpg, mp4), ~59 MB |
| `workspace/profile-images/` | `~/workspace/profile-images` | Profile reference image |
| `tools/bin/bws` | `~/tools/bin/bws` | Bitwarden Secrets Manager CLI binary (bws 2.1.0, 12.3 MB) — part of the binary-backup set; a real standalone file, not a nix/dispatcher artifact |
| `notes/disk-listings/` | `~/notes/disk-listings` | Gzipped full-disk file listings from 2026-09-30, ~10 MB |

## The rules (git vs. bucket vs. Drive)

From the 2026-10-21 research into GitHub's documented limits:

- **Per file: hard block at 100 MB** (warning above 50 MiB). Nothing over
  100 MB ever gets committed here — no exceptions, no split-file schemes.
- **Repo size: keep it ideally under 1 GB, strongly under 5 GB.** This drawer
  starts at ~81 MB.
- **Pushes are hard-limited to 2 GB** — bulk additions go up in slices.
- **Plain git only: no Git LFS** (metered quotas, every version counts in
  full) and no release-asset parking inside this repo's workflow.
- **Text and curated docs** belong in `dezren39/hatch` itself, not here.
  This drawer is for bulk and binaries.
- **Reproducible bulk never comes here at all**: no nix store, no caches,
  no language/toolchain trees, no `node_modules`, no repo clones, no
  browser binaries. Those are reinstalled from their install scripts/docs.
- **Single files over 100 MB** go to object storage / Google Drive, not git:
  new bulk originals → **R2** (zero egress) as the overflow path, with **B2
  as a mirror for the irreplaceable**. The current Drive-held items are
  listed below.
- **Secrets never go in git, public or private.** Credential values live in
  Bitwarden Secrets Manager; this drawer was pattern-scanned before its
  first commit.

## Held in Drive instead (>100 MB, never in git)

These live in the Google Drive folder **"Muse Backups"**
(`1FN6_rBX6mlll8uvkArW1ga0UoLK6Tm0T`):

- **`opt-backup.tar.zst`** — 1.08 GB snapshot of `/opt` from 2026-09-29
  (platform content: `opt/hatch`, `opt/hatch-image`, `opt/meta-chromium`).
  Uploaded 2026-10-21 as `opt-backup-UNDATED-uploaded-2026-10-21.tar.zst`,
  MD5-verified against the local copy.

Two further >100 MB items are listed in the private drawer's README, where
they belong.
