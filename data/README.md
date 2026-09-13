# Data

This directory is the committee data area for the GM-TSA / TCPR study.

The analysis dataset contains **91,186 player-event observations from 689 professional tournaments** spanning 2022 through July 2026. Development is 2022–2025; validation is 2026. Player names are excluded and player identifiers are anonymized.

## Analysis-ready columns

The full player-event file used for modeling contains tournament metadata, anonymous player ID, pre-tournament field rank, pre-tournament OWGR rank, logarithmic rank deficit, GM-TSA event strength, pre-event SGWR and Performance Points (including within-field percentiles), finish/status fields, and made-cut / Top-20 / Top-10 / Top-5 targets.

A 20-row audit sample is committed as `tcpr_player_event_sample_20.csv`. The full committee package prepared for this repository contains:

- `tcpr_player_event_analysis_data.csv.gz` — full 91,186-row anonymized player-event file
- `tcpr_event_level_gm_tsa.csv` — 689-event field-strength table
- `tcpr_player_event_sample_500.csv` — readable audit sample
- `dataset_summary.json` — dataset counts/splits

Source provenance and licensing are documented in `../DATA_SOURCES.md`; definitions are in `../DATA_DICTIONARY.md`.
