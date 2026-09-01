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

## Multi-device Co-location Features (`data/processed/calibration_validation/multidevice_colocation_2026-09-01_*`)

Second, independent in-situ check: ten production nodes co-located on one bench with
a UMIK-1 reference microphone for one continuous ~24.8 min ambient session
(2026-09-01). Device series carry only a server-ingest timestamp and are aligned to
the reference by a per-device cross-correlation lag search; metrics are computed on
lag-aligned 10 s bins. Node IDs are anonymised to `N01`..`N10`.

- `*_per_device_metrics_public.csv`: one row per node — `node`, `device_id`
  (opaque hash), `n`, `lag_s`, `xcorr_r`, `r`, `device_mean_db`,
  `reference_mean_db`, `bias_db`, `mae_db`, `rmse_db`, `response_slope`,
  `response_intercept`, `corr_slope`, `corr_intercept`, `corr_rmse_db`
  (residual RMSE after an in-sample per-device inverse linear fit).
- `*_fleet_summary_public.csv`: session and fleet aggregates (mean bias,
  inter-device SD, pooled MAE/RMSE, slope spread, fleet-offset residual).
- `*_aligned_10s_public.csv`: tidy aligned samples — `node`, `bin_start_utc`,
  `device_db`, `reference_db`, `error_db`.

Headline: median aligned r 0.72; fleet mean bias +4.3 dB; inter-device bias SD
7.0 dB; device-vs-reference slopes 1.3–2.8 (gain error, not offset-only).
This is an uncontrolled ambient-stimulus bench check, not a certified campaign.
