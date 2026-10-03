# fpwiki-content

Content corpus served by [fpwiki](https://github.com/ondrahracek/fpwiki).

This repo holds two directories:

- `content/` — markdown pages (courses, topics, summaries, outputs, plus the
  `_index.md` descriptions catalog)
- `wiki-assets/` — images embedded by those pages via `![[…]]` syntax

Everything here is populated by an **automated content pipeline**. Both
directories are fully overwritten on every sync — the publisher uses
`rsync --delete`, so any file present here that the upstream source no
longer has will be removed on the next push.

## Do not open pull requests against this repo

Any change you make will be wiped by the next sync. This repo is a
publication target, not an editing surface.

If you want to fix a typo or contribute content, open an issue on
[fpwiki](https://github.com/ondrahracek/fpwiki/issues).

## How fpwiki consumes this repo

fpwiki's build script downloads a tarball of this repo at a pinned commit
SHA (recorded per branch in fpwiki's `content-ref/<branch>.txt`) and extracts it into fpwiki's
`content/` and `public/wiki-assets/` directories. fpwiki itself never
tracks those files — this mirror is the only place they live in git.

That means:

- The deployed site at https://fpwiki.cz reflects whatever this repo's
  `master` branch contained at the time of fpwiki's last build.
- A specific fpwiki commit pins to a specific commit here, so historical
  fpwiki builds are reproducible.

## Branches

- `master` — content for fpwiki's production branch (deployed to
  https://fpwiki.cz)
- `test` — preview content for fpwiki's `test` branch (CI / local dev)

Branch names here mirror the consuming branch in fpwiki one-to-one.

## License

Currently unlicensed (matching fpwiki). The repo is publicly viewable but
not freely redistributable. A formal license will be added in coordination
with fpwiki.