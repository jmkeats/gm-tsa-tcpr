# Data Dictionary

## Player-event analysis data

Files: `data/parts/tcpr_player_event_part_*.csv.gz` (collectively 91,186 player-event rows)

| Field | Definition |
|---|---|
| `event_name` | OWGR tournament/event name. |
| `tour` | Tour designation associated with the event. |
| `event_date` | Event date recorded in the research dataset. |
| `owgr_event_id` | OWGR event identifier. |
| `source_url` | Public OWGR event source URL. |
| `season_year` | Calendar season used for study splitting. |
| `analysis_split` | `development_2022_2025` or `validation_2026`. |
| `field_size` | Number of players in the tournament field. |
| `anonymous_player_id` | Anonymous project identifier; player name is not included. |
| `pre_tourney_field_rank` | Player's ordinal slot within the tournament field before the event. |
| `current_owgr_rank` | Player's pre-tournament Official World Golf Ranking. |
| `rank_deficit_D` | `ln(current_owgr_rank / pre_tourney_field_rank)`. D=0 is the idealized slot-equals-rank benchmark. |
| `event_gm_value_pct` | Event-level geometric-mean field-strength quantity used as GM-TSA event context. |
| `geomean_field_strength_score` | Rounded/summary geometric-mean field-strength score from the source research dataset. |
| `strokes_gained_world_rating` | Pre-event Strokes Gained World Rating (SGWR). |
| `sgwr_within_field_percentile` | SGWR converted to a percentile within that event field. |
| `performance_points` | Pre-event Performance Points value. |
| `performance_points_within_field_percentile` | Performance Points converted to a percentile within that event field. |
| `actual_finish_numeric` | Numeric finishing position where available. |
| `actual_result_status` | Recorded result status. |
| `target_made_cut` | Binary made-cut target used for validation. |
| `target_top_20` | Binary Top-20 outcome. |
| `target_top_10` | Binary Top-10 outcome. |
| `target_top_5` | Binary Top-5 outcome. |

## Event-level data

File: `data/tcpr_event_level_gm_tsa.csv`

Contains one row per OWGR event used in the study, including event identity, source URL, field size, season, and GM-TSA/event-strength quantities.

## Missingness

The full player-event research dataset contains 91,186 rows. The raw 2026 portion contains 31,809 rows. The reported held-out validation sample contains 30,711 complete scored player-events after requiring the pre-tournament rank information and outcome fields used in the validation analysis.

Unranked/missing OWGR values are left missing in derived `rank_deficit_D` rather than replaced with invented ranks.
