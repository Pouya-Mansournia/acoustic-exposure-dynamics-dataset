# Data Dictionary

## Public deployment labels

- `Deployment_A`: main multi-floor office deployment.
- `Deployment_B`: separate one-floor comparison deployment.

## Common identifiers

- Sensor and node fields contain public pseudonyms only.
- Floor fields contain anonymized labels only.
- Period fields contain anonymized sequential or aggregate categories.

## Acoustic features

- `mean_db`, `median_db`, `std_db`: summaries of firmware-reported SPL-like dB values.
- Quiet/high-level shares: proportions below or above stated descriptive thresholds.
- `exposure_variability_index`: provisional rank composite; not a health or compliance metric.
- Pairwise correlation and approximate distance fields: exploratory synchrony/topology descriptors.

## Single-device reference comparison

- `elapsed_seconds`: elapsed time replacing the original timestamp.
- `acust_device_db`, `umik1_reference_db`: aligned one-second means.
- `error_device_minus_ref`: device minus reference.
- Band summaries report sample count, bias, MAE, and RMSE.

## Ten-device reference comparison

Files beginning `multidevice_colocation_2026-09-01_` describe one uncontrolled
24.8-minute ambient bench session. The filename records the experiment date,
but row-level timestamps and hardware IDs are removed.

- `*_aligned_10s_public.csv`: `elapsed_s`, pseudonymous `node`, `device_db`,
  `reference_db`, and `error_db`.
- `*_per_device_metrics_public.csv`: sample count, lag, correlations, device and
  reference means, bias, MAE, RMSE, response regression, and in-sample inverse-fit
  residual RMSE. No hardware identifier is included.
- `*_fleet_summary_public.csv`: session duration and fleet summaries without
  start/end timestamps.
- `device_cluster_uncertainty_public.csv`: device-cluster bootstrap intervals.
- `chronological_holdout_*_public.csv`: first-half-fit/second-half-test results
  within the same ambient session.
- `historical_correction_transfer_*_public.csv`: transfer of the archived
  single-device affine correction without refitting.

These fields do not establish formal calibration, frequency-response flatness,
A-weighting, IEC 61672 conformity, or performance of newer firmware.
