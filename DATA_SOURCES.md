# Data Sources and Attribution

## Primary source

All underlying professional-golf ranking and tournament data used in this research were obtained from publicly available pages on the **Official World Golf Ranking (OWGR)** website.

The analysis dataset retains the public OWGR event URL in the `source_url` field so that tournament-level source records can be traced and reviewed.

Source website: https://www.owgr.com/

## What is source data vs. derived research data

Examples of source or source-derived OWGR fields used in the project include:

- tournament/event identity
- tour
- event date
- field size
- pre-tournament OWGR rank
- tournament field slot
- Strokes Gained World Rating (SGWR)
- Performance Points
- tournament result / finishing outcome

Research variables created for this project include:

- logarithmic rank deficit `D = ln(R/j)`
- GM-TSA tournament-strength representation
- within-field SGWR percentile
- within-field Performance Points percentile
- development/validation split labels
- TCPR model outputs and validation statistics
- bootstrap confidence intervals and ranking diagnostics

## Licensing note

The repository's MIT License applies to original code, scripts, documentation, and analytical methods created for this project.

The underlying OWGR data and factual records are attributed to OWGR and are not claimed as original intellectual property of the author and are not relicensed under the MIT License merely because they were publicly accessible.

Users of this repository should independently comply with OWGR's applicable terms when reusing source data.

## Reproducibility and review

The repository includes the anonymized player-event analysis dataset used in the study rather than requiring reviewers to reconstruct the dataset from the live website. Event URLs are retained for source traceability.
