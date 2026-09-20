# GM-TSA / Tournament-Conditioned Player Rating (TCPR)

This repository contains the data package supporting:

**Same Rank, Different Tournament: A Tournament-Conditioned Player Rating for Professional Golf**

**Start here for SSAC review:** [`paper/ABSTRACT.md`](paper/ABSTRACT.md) — updated abstract and supporting forward-validation table. The author’s updated Word draft is not yet committed to this repository; do not treat a named PDF or DOCX as available until its file is visible in `paper/`.

Author: **John M. Keating, MBA**

## Research question

The Official World Golf Ranking (OWGR) provides a global ordering of professional golfers, but a global rank can have different competitive meaning in tournament fields of different strength. This project introduces:

- **GM-TSA (Geometric-Mean Tournament Strength Adjustment)**: an event-level measure of tournament field strength relative to an idealized slot-equals-rank benchmark.
- **TCPR (Tournament-Conditioned Player Rating)**: a pre-event player-rating framework combining tournament-relative field position, logarithmic rank deficit, GM-TSA event strength, and pre-event form variables.

The core rank-deficit quantity is:

`D(i,e) = ln(R(i,e) / j(i,e))`

where `R(i,e)` is the player's pre-tournament OWGR rank and `j(i,e)` is the player's tournament field slot.

The event-level GM-TSA definition used in the paper is:

`GM-TSA(e) = 100 * exp[(1/N(e)) * sum_i ln(j(i,e) / R(i,e))]`

## Study design

- 91,186 player-event observations
- 689 professional tournaments
- 2022 through July 2026
- Model development: 2022-2025 only
- Forward validation: 2026 only
- Model coefficients were frozen before the 2026 validation period
- Player names and direct identifiers are excluded from the model data
- All model features are pre-tournament

The held-out 2026 analysis used 30,711 complete scored player-events.

## Key forward-validation results

| Outcome | OWGR AUC | Field-rank AUC | TCPR AUC | TCPR Brier |
|---|---:|---:|---:|---:|
| Made cut | 0.677 | 0.708 | 0.731 | 0.216 |
| Top 20 | 0.634 | 0.749 | 0.759 | 0.133 |
| Top 10 | 0.640 | 0.756 | 0.770 | 0.078 |
| Top 5 | 0.646 | 0.769 | 0.789 | 0.044 |

Incremental AUC versus field rank:
- Top 20: +0.010 (95% CI +0.006 to +0.013)
- Top 10: +0.014 (95% CI +0.010 to +0.017)
- Top 5: +0.020 (95% CI +0.016 to +0.025)

## Repository contents

- `data/parts/` - anonymized 91,186-row player-event analysis dataset, split into compressed CSV parts for GitHub review.
- `data/tcpr_event_level_gm_tsa.csv` - one row per OWGR tournament, including GM-TSA/event-strength fields.
- `data/tcpr_player_event_sample_500.csv` - human-readable sample of the analysis dataset.
- `data/dataset_summary.json` - row counts, event counts, seasons, and study splits.
- `DATA_DICTIONARY.md` - definitions of analysis fields.
- `DATA_SOURCES.md` - source attribution and licensing note.
- `results/tcpr_2026_validation_metrics.csv` - reported AUC, Brier score, and log-loss results.
- `results/tcpr_2026_auc_bootstrap_confidence_intervals.csv` - event-clustered bootstrap AUC confidence intervals.
- `figures/figure1_gm_tsa_tcpr_forward_validation.png` - figure used in the abstract package.
- `paper/ABSTRACT.md` - canonical updated abstract text, model definition and supporting validation table.
- The revised Word/PDF copies are pending upload to `paper/`; the README will link them when they actually exist.
- `analysis/REPRODUCIBILITY.md` - analysis and validation notes.

## Data source

All underlying golf ranking and tournament information used in this study was obtained from publicly available **Official World Golf Ranking (OWGR)** website pages. Event source URLs are retained in the research dataset so individual tournaments can be traced back to their public OWGR source pages.

See `DATA_SOURCES.md` for attribution and licensing details.

## Anonymization

Player names are not included in the committee analysis dataset. `anonymous_player_id` is retained only to support within-player analytical checks where needed. No personal contact or sensitive information is included.

## License

The MIT License applies only to original code, scripts, documentation, and analytical material created for this project. OWGR source data and facts are attributed to OWGR and are **not relicensed under the MIT License**.

## Citation

Keating, John M. (2026). *Same Rank, Different Tournament: A Tournament-Conditioned Player Rating for Professional Golf.*
