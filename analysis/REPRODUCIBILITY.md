# Reproducibility Notes

## Temporal design

The analysis intentionally separates model development from forward validation:

1. **Development:** 2022-2025 tournaments only.
2. Model specification and coefficients are frozen.
3. **Validation:** 2026 tournaments only.
4. No player name or player identity is used as a predictive feature.
5. No post-event information is used as a predictor.

This design is intended to reduce look-ahead bias and test whether the tournament-conditioned rating generalizes prospectively.

## Core structural quantities

For player `i` in event `e`:

`D(i,e) = ln(R(i,e) / j(i,e))`

where:
- `R(i,e)` = pre-tournament OWGR rank
- `j(i,e)` = pre-tournament tournament field slot

Event-level tournament strength is represented by:

`GM-TSA(e) = 100 * exp[(1/N(e)) * sum_i ln(j(i,e) / R(i,e))]`

where `N(e)` is the number of players in event `e`.

TCPR combines:
- tournament-relative field slot
- logarithmic rank deficit D
- GM-TSA event context
- interactions among the structural tournament-context variables
- pre-event SGWR, transformed to a within-field percentile
- pre-event Performance Points, transformed to a within-field percentile

## Validation outcomes

The frozen model was evaluated on:
- made cut
- Top 20
- Top 10
- Top 5

Reported diagnostics include:
- area under the receiver operating characteristic curve (AUC)
- Brier score
- log loss
- event-clustered bootstrap 95% confidence intervals
- Top-10 capture by predicted Top 20
- within-event Spearman rank correlation with finishing position

## Reported 2026 sample

The held-out validation contains **30,711 complete scored player-events across 252 tournaments**.

The repository's event table includes all 689 tournaments in the 2022-July 2026 research dataset; the player-event data parts collectively contain all 91,186 source analysis rows.

## Results files

`results/tcpr_2026_validation_metrics.csv` contains the exact metrics used for the abstract table.

`results/tcpr_2026_auc_bootstrap_confidence_intervals.csv` contains the event-clustered bootstrap confidence intervals for incremental AUC.

## Model code

The competition guidance states that model code is encouraged but not required. This repository prioritizes release of the exact anonymized analysis data, source tracing, definitions, validation metrics, and paper materials required to audit the research.

A future public release may add a fully packaged model-fitting notebook after the submission version is frozen. Any such addition should be versioned separately so that the data and reported submission results remain unchanged.
