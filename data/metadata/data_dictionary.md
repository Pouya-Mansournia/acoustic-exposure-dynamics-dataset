# Data Dictionary

## Common Identifiers

- `sensor_id`: anonymized sensor ID (`S001`, `S002`, ...).
- `floor`: anonymized floor label (`Floor_A`, `Floor_B`, ...).
- `company_id`: anonymized as `HQ_Anonymized`.
- `period_id`: anonymized sequential operational period label (`P001`, `P002`, ...), with original calendar identifiers removed.

## Acoustic Features

- `mean_db`: mean calibrated SPL-like dB over the aggregation unit.
- `median_db`: median calibrated SPL-like dB.
- `std_db`: standard deviation of dB values or minute aggregates.
- `quiet_share_50`: share of periods at or below 50 dB.
- `high_exposure_share_70`: share of periods at or above 70 dB.
- `exposure_variability_index`: rank-based index combining variability, high-exposure share, and non-quiet share.
- `profile_stability_score`: profile stability where computable.

## Pairwise Features

- `pearson_corr`: Pearson correlation of period-level mean dB between two sensors.
- `spearman_corr`: Spearman correlation of period-level mean dB between two sensors.
- `approx_distance`: normalized approximate map-plane distance.
- `same_floor`: whether the anonymized pair is on the same floor.

## Operational Features

- `event_type`: broad anonymized operational event label where available.
