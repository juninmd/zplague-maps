# AGENTS.md

Server-side content pack (maps, WADs, models, sounds, sprites, skyboxes) for a Counter-Strike 1.6 Zombie Plague 5.0 server. No code, no build step.

## Stack

- Game assets: `.bsp`, `.wad`, `.res`, `.nav`, `.mdl`, `.wav`, `.spr`, `.tga`, `.bmp`, `.txt`
- CI: GitHub Actions calling reusable workflows from `juninmd/base-actions`

## Commands

- Setup, dev, build, test, lint, typecheck: none. There is no local script and no map compile step.
- CI (`.github/workflows/`):
  - `validate.yml`: pull request and push to `master`
  - `security.yml`: push to `master`, weekly schedule, manual
  - `sast.yml`: push to `main` or `master`, manual (Semgrep is report-only)

## Structure

- `cstrike/`: server tree, merged into a server's `cstrike/` (never replaced whole)
  - `maps/`: `.bsp`, `.res`, `.nav`, `.txt`, per-map assets
  - `models/`, `sound/`, `sprites/`: per-map folders
  - `gfx/env/` skyboxes, `gfx/detail/` detail textures
  - `overviews/`: radar images and scripts
  - `*.wad`: shared and per-map WADs
- `meus_plugins_organizados/07-Resources/maps/`: archive area with `.rar` files and extracted copies, not a clean source tree
- `docs/readme/`: README images
- `README.md`: installation and inventory. `backlog.md`: research snapshot of missing popular maps

## Conventions

- Default branch: `master`.
- Keep the layout the server expects. Do not move assets: some maps ship models and sounds flat in `cstrike/maps/`, and the map refers to them by name.
- Do not add server configs, plugins, `mapcycle.txt` or AMX Mod X files. They come from the server setup, out of scope for this pack.
- Mixed-case filenames exist (for example `zm_LUZ.bsp`, `Zm_Ice_Abyss.bsp`). Linux servers are case-sensitive; keep exact names.

## Gotchas

<!-- base-actions-main-policy -->
- Reference internal actions by branch, never by SHA: `uses: juninmd/base-actions/<action>@main` and `uses: juninmd/base-actions/.github/workflows/<file>.yml@main`. Do not pin `@<sha>` for `juninmd/base-actions`; updates are centralized on `main`.
- PRs whose checks never start because of billing or spending limits are merged by `juninmd/base-actions/.github/workflows/auto-merge-billing-blocked.yml`. To block that merge for a PR, apply the label `do-not-merge`.
- Only 92 of 223 maps ship a `.res`. Clients depend on FastDL paths for the rest.
- The repo is large (about 560 MB). Use shallow or sparse clones (`git clone --depth 1 --filter=blob:none --sparse`).
