# Committee Package Manifest

This manifest lists GM-TSA / TCPR research-package artifacts and their recorded SHA-256 hashes. Some listed artifacts may be archived or awaiting upload; confirm actual repository presence before treating a path as available.

## Core documentation

- `README.md`
- `DATA_SOURCES.md`
- `DATA_DICTIONARY.md`
- `LICENSE`
- `CITATION.cff`
- `analysis/REPRODUCIBILITY.md`

## Data

- `data/tcpr_player_event_analysis_data.csv.gz` — anonymized 91,186-row player-event analysis file — SHA-256 `fe6986f37b84c24613426169e65458736cdbfaeba17733fba84c5014cc25d9c7`
- `data/tcpr_event_level_gm_tsa.csv` — 689-event field-strength table — SHA-256 `e83eea880254a84e625dd625c14dff91a1be267893dbbeae8e388e212eafae81`
- `data/tcpr_player_event_sample_500.csv` — readable audit sample — SHA-256 `4428b0c2822c79b687d34e0496d5f5caba45abeeb8b5239fd1a51466a9aaea74`
- `data/dataset_summary.json`

## Results

- `results/tcpr_2026_validation_metrics.csv` — SHA-256 `356b910f899789f5ad632d1b57f72901e969b77bb566ccb34ba49de690512009`
- `results/tcpr_2026_auc_bootstrap_confidence_intervals.csv` — SHA-256 `57fb3c291c481f4bb49c658639b81368ab05a8016478a25c883ac33e98cf6546`

## Figure and paper

- `figures/figure1_gm_tsa_tcpr_forward_validation.png` — SHA-256 `a8387f6e2cbeda5f1ca3ada5a60b40975d94acabd92b130013849ec55faeb2b7`
- `paper/ABSTRACT.md` — canonical updated SSAC abstract text and supporting table (present in repository).
- `paper/SSAC_Abstract_TCPR_Final.docx` — **not present in the repository as checked September 20, 2026**; historical recorded SHA-256 `aad893cc148e185d7d2b16874bfbee4a591c7fc6d7c0f0683f0e9b599b4e8f72` (does not describe the revised Word draft).
- `paper/SSAC_Abstract_TCPR_Final.pdf` — **not present in the repository as checked September 20, 2026**; historical recorded SHA-256 `f5d4600fd60f3c20cc224fbf22bcd7d9d0025582aadfe3a7cc016f167c6437d1`.

Until revised binary files are committed and hashes updated, reviewers should use `paper/ABSTRACT.md` for the updated abstract. Do not cite the historical binary hashes as hashes of the revised draft.

Underlying ranking and tournament information is attributed to the Official World Golf Ranking (OWGR). The MIT license applies only to original project code, scripts, documentation, and analytical materials; it does not relicense OWGR source data.
