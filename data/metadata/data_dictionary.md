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

## Calibration Validation Features (`data/processed/calibration_validation/`)

- `elapsed_seconds`: seconds elapsed since the start of the single co-location session (replaces the original wall-clock timestamp).
- `acust_device_db`: the Acust device's own calibrated dashboard/MQTT-reported dB value, 1 s bin mean.
- `umik1_reference_db`: the co-located UMIK-1 reference microphone's reported dB, 1 s bin mean, after cross-correlation time alignment.
- `error_device_minus_ref`: `acust_device_db - umik1_reference_db` for that 1 s bin.
- `bin`: UMIK-1 reference SPL band (`<60`, `60-70`, `70-80`, `>=80` dB) used in the by-band summary file.
- `n`, `bias`, `mae`, `rmse`: sample count, mean error, mean absolute error, and root-mean-square error of `error_device_minus_ref` within each band.
