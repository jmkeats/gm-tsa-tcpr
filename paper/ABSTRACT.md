# Same Rank, Different Tournament: A Tournament-Conditioned Player Rating for Professional Golf

**John M. Keating, MBA**  
SSAC Research Paper Competition | Abstract and supporting material

## Introduction
The Official World Golf Ranking (OWGR) provides global ordering of professional golfers, but it does not explicitly quantify what that ordering means inside tournament fields of different strength. Geometric-Mean Tournament Strength Adjustment (GM-TSA) treats an idealized strongest field as one in which field slot j is occupied by world rank j, then measures how actual fields depart from that benchmark. We test whether this tournament-conditioned structure can support an identity-agnostic pre-event player rating that adds predictive information beyond both global OWGR and simple tournament-relative field rank.

## Methods
We analyzed 91,186 player-event observations from 689 professional tournaments (2022–July 2026). All model development used 2022–2025 data; coefficients were frozen before 2026 validation. For player i in event e, field slot j and pre-tournament OWGR rank R define a logarithmic rank deficit D = ln(R/j); event GM-TSA is the geometric mean of j/R across the field. We define the Tournament-Conditioned Player Rating (TCPR) as the model combining field slot, D, GM-TSA event strength and their interactions with pre-event Strokes Gained World Rating (SGWR) and Performance Points, each transformed to within-field percentiles. No player identity or post-event information entered the model. We compared OWGR, tournament-relative field rank, and TCPR on 2026 made-cut, Top-20, Top-10, and Top-5 outcomes using area under the receiver operating characteristic curve (AUC), Brier score, log loss, event-clustered bootstrap confidence intervals, Top-10 capture, and within-event Spearman rank correlation.

## Results
The held-out 2026 sample contained 30,711 scored player-events across 252 tournaments. For Top-20, Top-10, and Top-5 prediction, OWGR alone produced AUCs of 0.634, 0.640, and 0.646. Converting OWGR to tournament-relative field rank increased these to 0.749, 0.756, and 0.769, showing that event context itself materially changes the information content of global rank. TCPR improved further to 0.759, 0.770, and 0.789. Relative to field rank, incremental AUC was +0.010 for Top 20 (95% CI +0.006 to +0.013), +0.014 for Top 10 (+0.010 to +0.017), and +0.020 for Top 5 (+0.016 to +0.025). For made-cut prediction, TCPR AUC was 0.731 versus 0.677 for OWGR. TCPR’s predicted Top 20 captured 46.1% of actual Top-10 finishers versus 44.6% for field rank, while median within-event Spearman correlation with finishing position improved from 0.331 to 0.360.

## Conclusion
Tournament context changes the practical meaning of a global ranking. OWGR supplies global ordering; GM-TSA quantifies the competitive environment, and TCPR converts both into a tournament-specific player expectation that can be adjusted using only pre-event form. The significant prospective gains over tournament-relative field rank indicate that the framework adds information rather than merely repackaging OWGR. This complementary approach may improve tournament forecasting, player valuation, exemption decisions, and field-quality analysis.

## Supporting model definitions (outside abstract)

The abstract above is the canonical text of the updated Word draft supplied by the author. Supporting material below is separate from the abstract word count.

## Model definition

`D_(i,e) = ln(R_(i,e) / j_(i,e))`

`GM-TSA_e = 100 exp[(1/N_e) Σ_(i=1)^(N_e) ln(j_(i,e) / R_(i,e))]`

The benchmark `D_(i,e)=0` corresponds to the idealized slot-equals-rank condition.

## Supporting forward-validation table

| Outcome | OWGR AUC | Field-rank AUC | TCPR AUC | Δ vs OWGR | Δ vs field rank | TCPR Brier |
|---|---:|---:|---:|---:|---:|---:|
| Made cut | 0.677 | 0.708 | 0.731 | +0.053 | +0.023 | 0.216 |
| Top 20 | 0.634 | 0.749 | 0.759 | +0.125 | +0.010 | 0.133 |
| Top 10 | 0.640 | 0.756 | 0.770 | +0.130 | +0.014 | 0.078 |
| Top 5 | 0.646 | 0.769 | 0.789 | +0.144 | +0.020 | 0.044 |

**Numerical verification note:** Incremental AUC values are reported from the unrounded model outputs in `results/tcpr_2026_validation_metrics.csv` and `results/tcpr_2026_auc_bootstrap_confidence_intervals.csv`, then rounded for presentation.
