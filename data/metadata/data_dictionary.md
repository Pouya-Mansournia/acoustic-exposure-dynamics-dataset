# Data Dictionary

## Public Deployment Labels

- `Deployment_A`: main multi-floor office deployment.
- `Deployment_B`: independent one-floor validation deployment.

## Common Identifiers

- `sensor_id`, `sensor`, `sensor_a`, `sensor_b`: public pseudonymized sensor IDs.
- `floor`, `floor_a`, `floor_b`, `anonymized_floor`: public pseudonymized floor labels.
- `period_id`: anonymized sequential period label. Original dates and clock labels are removed.

## Acoustic Features

- `mean_db`: mean calibrated SPL-like dB over the aggregation unit.
- `median_db`: median calibrated SPL-like dB.
- `std_db`: standard deviation of dB values or period aggregates.
- `quiet_share_50`, `quiet55_diff`: quiet-period share or difference.
- `high_exposure_share_70`, `high70_diff`: high-exposure share or difference.
- `exposure_variability_index`: descriptive composite combining variability, high-exposure share, and non-quiet share.

## Pairwise Features

- `pearson_corr`, `spearman_corr`, `correlation`: pairwise synchrony metrics.
- `approx_distance`: normalized approximate map-plane distance.
- `same_floor`: whether the public pair is on the same anonymized floor.

## Operational Features

- `event_type`: broad operational event label where available.
- `operational_group`: broad operational category used in aggregate analysis.

These fields are aggregate research features and should not be interpreted as source labels, speech labels, occupancy counts, or room-acoustic parameters.
