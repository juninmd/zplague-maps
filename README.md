# zplague-maps

**Non-default map pack for a Zombie Plague 5.0 server on Counter-Strike 1.6.**

This repository collects the maps, WADs, models, sounds, sprites and skyboxes needed to run a Zombie Plague server with the `zplague-addons` setup. It is a server-side content pack: no plugins, no AMX Mod X configuration and no map cycle are included.

The pack contains **226 `.bsp` files**: 223 maps under `cstrike/maps/` and 3 more inside the archive area in `meus_plugins_organizados/07-Resources/maps/`. The 223 maps in the live tree are the ones available from `cstrike/maps/`.

## What is in the pack

| Component | Count | Location |
|---|---|---|
| Maps | 223 `.bsp` in the live tree | `cstrike/maps/` |
| Map resources | 90 `.res` | `cstrike/maps/` |
| Bot navigation | 7 `.nav` | `cstrike/maps/` |
| Map text files | 68 `.txt` | `cstrike/maps/` |
| Map props and sounds | 119 `.mdl`, 40 `.wav`, 5 `.spr` | `cstrike/maps/` |
| WADs | 19 `.wad` | `cstrike/` |
| Models | 357 files | `cstrike/models/` |
| Sounds | 235 files | `cstrike/sound/` |
| Sprites | 46 files | `cstrike/sprites/` |
| Skyboxes | 199 textures | `cstrike/gfx/env/` |
| Detail textures | 11 textures | `cstrike/gfx/detail/` |
| Radar images | 28 images plus 23 `.txt` | `cstrike/overviews/` |

Some maps ship their own models and sounds flat inside `cstrike/maps/` instead of a per-map folder. Keep those files where they are; the map refers to them by name.

## Requirements

- A Counter-Strike 1.6 dedicated server.
- Zombie Plague 5.0 from the `zplague-addons` collection.
- Enough disk space for the maps and the client download mirror.
- HTTP FastDL is strongly recommended. Without it, every client needs the `.bsp`, `.wad`, models, sounds and sprites installed locally, or the map will fail to load.

This pack does not include the game server, the Zombie Plague plugin, AMX Mod X or a `mapcycle.txt`. Those come from your existing server setup.

## Installation

1. Back up the server's `cstrike/` directory.
2. Copy the **contents** of this repository's `cstrike/` into the server's `cstrike/`, merging folders. Do not replace the whole `cstrike/` directory, or you will lose the server's existing configuration.
3. Confirm that `cstrike/maps/`, `cstrike/models/`, `cstrike/sound/`, `cstrike/sprites/`, `cstrike/gfx/env/` and the WADs in `cstrike/` all landed in the server tree.
4. Mirror the same relative paths on your FastDL host. Clients download `.bsp`, `.res`, `.wad`, `.mdl`, `.wav` and `.spr` files from there.
5. Add the map names you want to your existing map cycle or admin menu. The names are the `.bsp` filenames without the extension.
6. Change to a map and test it with a real client, not only with the server console.

The `cstrike/maps/README!.txt` file is an author note (it credits `Nazi.-`), not installation documentation for the pack.

### About `.res` files

A `.res` file tells the client which extra files to download for a map. Only 90 of the 223 live maps include one. For the other maps, client downloads depend on your FastDL mirror and on the client already having the right WADs, models and sounds. If a map loads on the server but clients disconnect or see missing textures, check the FastDL paths first.

## Folder layout

```text
cstrike/
├── maps/                 # .bsp, .res, .txt, .nav and some per-map assets
├── models/               # per-map model folders
├── sound/                # per-map sound folders
├── sprites/              # per-map sprite folders
├── gfx/
│   ├── env/              # skybox textures
│   └── detail/           # detail textures
├── overviews/            # radar images and overview scripts
└── *.wad                 # shared and per-map WADs
meus_plugins_organizados/
└── 07-Resources/maps/    # .rar archives and extracted copies
```

## Map inventory

The live tree is dominated by `zm_` maps. The rest are escape, arena, boss and classic layouts.

| Prefix | Maps | Notes |
|---|---:|---|
| `zm_` | 191 | Zombie Plague maps, the bulk of the pack |
| `bio_` | 6 | Biohazard-themed maps |
| `zp_` | 5 | Maps using the older `zp_` naming |
| `ze_` | 4 | Escape maps |
| `zs_` | 3 | Arena and boss names |
| `cs_` | 3 | Classic Counter-Strike layouts |
| `ne_` | 3 | Pool day variants |
| `de_` | 2 | Defusal layouts |
| `zl_` | 2 | Boss maps |
| `mg_` | 1 | Mini-game map |
| `vip_` | 1 | VIP map |
| `za_` | 1 | Map using the `za_` prefix |
| no prefix | 1 | `soccerjam` |

<details>
<summary>Full list of the 223 maps in cstrike/maps</summary>

**`zm_` (191)**

`zm_2day`, `zm_2day_2`, `zm_303`, `zm_357_beta`, `zm_3rooms`, `zm_3rooms_v2_fix`, `zm_4_tours_fix`, `zm_747_b2_zg`, `zm_abyss2`, `zm_allestreet`, `zm_anubis`, `zm_apparition`, `zm_arctic`, `zm_arctic_fun_2016`, `zm_ark_ice_defense_v1`, `zm_army`, `zm_army_tn_beta3`, `zm_austria_clocktower_zg`, `zm_austria_mansion_zg`, `zm_austria_square_zg`, `zm_aztec`, `zm_aztec_infinity`, `zm_battleground_foda`, `zm_biohazard_base_mx`, `zm_boatescape`, `zm_cantera`, `zm_canyon`, `zm_casttle_b2k`, `zm_cave_new`, `zm_cave_v2_re`, `zm_clifa`, `zm_colabase`, `zm_cold_attack`, `zm_compilation`, `zm_cornered`, `zm_covid2020`, `zm_cpl_egyptian`, `zm_crib`, `zm_cross`, `zm_crossice_b2_zg`, `zm_csdevils`, `zm_csgo_train_v2017`, `zm_cubeworld`, `zm_cubeworld_mini`, `zm_dark_map_2011`, `zm_deadcity_play4ever`, `zm_decline2k`, `zm_ded_street3`

`zm_deko2`, `zm_desert_2011`, `zm_desertcomplex`, `zm_desertlab`, `zm_desolation_house`, `zm_dogle`, `zm_downtown`, `zm_dust_undead`, `zm_dust_world`, `zm_dust2`, `zm_dust2_2k15`, `zm_dust2_2x2`, `zm_dust2_new`, `zm_dust2x2_remake`, `zm_dusts`, `zm_dustx2`, `zm_dwarf_ultimate`, `zm_effect`, `zm_electro_winter`, `zm_f_garden`, `zm_fg_anekin_remix`, `zm_fg_christmas`, `zm_fg_czeko`, `zm_fg_fox_xmas`, `zm_fg_graveyard_rd`, `zm_fg_perfect_halloween`, `zm_five`, `zm_five_reborn`, `zm_fix_vk`, `zm_flood`, `zm_force`, `zm_forested`, `zm_fox`, `zm_freebase`, `zm_fun_world_allstars`, `zm_G1_city`, `zm_gbox6`, `zm_gbox7`, `zm_gg`, `zm_gNight_snowbase`, `zm_gNight_toxicriver`, `zm_gorod_final`, `zm_gtex`, `zm_halloween`, `zm_heal_dust2`, `zm_heal_snow2`, `zm_heal_void`, `zm_highrise3`

`zm_hotline`, `zm_house_xmasv2`, `zm_huebunker`, `Zm_Ice_Abyss`, `zm_ice_attack`, `zm_ice_attack2`, `zm_ice_attack3`, `zm_ice_attackv4_v3`, `zm_ice_castlev1`, `zm_ice_vk`, `zm_india`, `zm_infancy`, `zm_infantry`, `zm_inferno`, `zm_inferno_re_v2`, `zm_kill_duster`, `zm_ko_catacombs`, `zm_lab7K`, `zm_LabU`, `zm_laura`, `zm_lent_zone`, `zm_long_night_v2`, `zm_lostproject`, `zm_ls_construct`, `zm_ls_subzero`, `zm_LUZ`, `zm_mario_world_new`, `zm_meat_industry_b3`, `zm_megahard`, `zm_mini_rpd`, `zm_mkdualdust`, `zm_nightmare`, `zm_nose`, `zm_office_b2`, `zm_orange`, `zm_orlingbase_new`, `zm_pharaoh`, `zm_pool_day`, `zm_prospeedball_v2`, `zm_q3_DarkBishop_v11`, `zm_QueenS_d2`, `zm_rats_v2`, `zm_refuge_small_ult_4`, `zm_restart_v3`, `zm_riverside`, `zm_Rooms_Roz_u2`, `zm_roscoe_street`, `zm_roz_appall_v1`

`zm_rufflejungle`, `zm_sand_new`, `zm_silent_hill`, `zm_small_dust_classic`, `zm_snow_valley_cso_final`, `zm_snowbase`, `zm_snowbase2`, `zm_snowytundra`, `zm_spacelab`, `zm_stellar_facility`, `zm_stz`, `zm_sursista_new_v1`, `zm_sursista_new_v2`, `zm_sursista_new_v3`, `zm_sursista_new_v4`, `zm_sursista_new_v5`, `zm_sursista_new_v6`, `zm_sweets`, `zm_tac_snowbattle_v1`, `zm_talvisota`, `zm_tehina`, `zm_terial`, `zm_texas_night`, `zm_thunderclap`, `zm_tonga_remake`, `zm_toronto_new2`, `zm_toronto2015`, `zm_tower_new`, `zm_towning`, `zm_toxic_house_vk`, `zm_toxic_ice_attack2`, `zm_train`, `zm_trains`, `zm_universe`, `zm_vicetone_rajagame`, `zm_vintage3`, `zm_virus_t`, `zm_volcano`, `zm_vtf_corp`, `zm_western`, `zm_xopom_town`, `zm_zhell`, `zm_zod_down_river`, `zm_zombattack_new`, `zm_zombie_land_nD`, `zm_zombust`, `zm_zow_funzone_1`

**Other prefixes (32)**

`bio_beach`, `bio_mystery`, `bio_oldhouse`, `bio_oldhouse_winter`, `bio_ruins_b4`, `bio_survivor`

`zp_andromeda_dg`, `zp_blackmesa`, `zp_mutated_city`, `zp_mutated_city_v2`, `zp_zplague_ice`

`ze_campescape_lg`, `ze_egypt_two_lg`, `ze_jurassicpark4`, `ze_potc_fabi`

`zs_frozen_boss`, `Zs_Angra_Nest`, `Zs_Revenant_Arena`, `zl_boss_alien`, `zl_boss_scorpion_alpha`

`cs_assault_city2`, `cs_metro`, `cs_narodniy`, `de_radwaste`, `de_railroad`, `ne_pool_day`, `ne_pool_day_arena`, `ne_pool_day_se`

`mg_trafficlight_c2`, `soccerjam`, `vip_truck32`, `za_crossfire_b7_zg`

</details>

### The three extra `.bsp` files

`meus_plugins_organizados/07-Resources/maps/` contains archived map packages:

- `vip_truck32.bsp` and `zp_zplague_ice.bsp` are duplicates of maps already present in `cstrike/maps/`.
- `zm_evento_galinhazplague.bsp` exists only in the archive folder, inside `zm_evento_galinhazplaguee/maps/`, together with three WADs and a `.pts` file.
- `zm_fun_world_zplague.rar` and `zp_zplague_nw_final.rar` are archives that were not extracted in the repository.

## Content ownership and licensing

The maps, models, sounds, sprites, textures and WADs were made by different authors in the Counter-Strike modding community. This repository is a collection for a Zombie Plague server; it does not relicense any of the content and does not grant rights to redistribute it.

- There is **no license file** in this repository.
- Some maps include the author's own readme with credits or usage notes. Keep those files with the maps.
- If you mirror this pack publicly, on FastDL or anywhere else, check the terms of each original author. A public mirror is a redistribution, not a personal copy.
- If an author asks for removal, remove the map and its assets.

The repository's role is to keep a working server pack together, not to claim authorship or ownership of the maps.

## Limitations

- **No test results are included.** A map may load but have missing textures, broken spawns or require a specific plugin version.
- **`.res` coverage is partial.** Only 90 of 223 maps ship a `.res`; clients may fail to download the rest if FastDL is incomplete.
- **Radar coverage is partial.** Only 28 overview images are present for 223 maps.
- **Bot navigation is partial.** Only 7 maps include a `.nav` file.
- **Case matters.** The pack has mixed-case filenames such as `Zm_Ice_Abyss.bsp`, `Zs_Angra_Nest.bsp`, `zm_LUZ.bsp` and `zm_G1_city.bsp`. A Linux server with a case-sensitive filesystem needs the exact names.
- **The archive folder is not a clean source tree.** It contains `.rar` files alongside extracted copies, and two archives were not extracted.
- **No server configuration is included.** There is no map cycle, no Zombie Plague config and no plugin list.
- **`backlog.md` is a research snapshot, not a guarantee.** It lists popular maps that are still missing, such as `zm_foda`, `zm_fdust2x2` and `zm_zero_blood`, based on server rankings consulted on 2026-10-21. Download links for those maps were not verified.

## Repository automation

There is no build or map compile step. CI only calls the shared reusable workflows from `juninmd/base-actions`:

| Workflow | Trigger |
|---|---|
| `validate.yml` | Pull request and push to `master` |
| `sast.yml` | Push to `main` or `master`, and manual dispatch; Semgrep findings are report-only |
| `security.yml` | Push to `master`, weekly schedule, and manual dispatch |
| `dependabot-auto-merge.yml` | Dependabot pull requests, merged when all checks pass |

## Related

- `backlog.md` — list of popular maps missing from the pack and the sources used to rank them.
- `zplague-addons` — the companion Zombie Plague 5.0 plugin and addon collection used with this map pack. It is a separate, private repository and is not included here.
