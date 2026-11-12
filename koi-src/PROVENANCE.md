# Provenance

Vendored from https://github.com/yalongwastaken/git-koi (MIT, see LICENSE)
at commit `7305e9b1fadee6f43d3b4fa543a25d4cde79856e` (tag v1.0.2), reviewed
2026-11-12.

Only `src/`, `Cargo.toml`, `Cargo.lock`, and `LICENSE` were copied. Upstream's
workflows, Action, tests, examples, and docs were left out. The one local
change: `Cargo.toml`'s `readme` points at `UPSTREAM-README.md`.

Updating is a deliberate act: re-review the upstream diff, then copy the new
files over these. Nothing here updates on its own.

Security notes from the review:

- The only process it spawns is `gh api graphql` with read-only queries for public
  data (`privacy: PUBLIC`). It makes no other network calls and has no `unsafe`.
- `render` is pure in-memory drawing; it writes only koi.gif, koi.png, and
  preview.html (static, no scripts) into the output directory.
- Dependencies: chrono, gif, png, serde, serde_json, pinned with checksums in
  Cargo.lock.
