# Privacy and Limitations

## Privacy Transformations

- Raw audio is not included and was not stored by the analyzed system.
- Raw sound logs are not included.
- Exact calendar dates, weekday labels, and clock times are removed.
- Sensor IDs are pseudonymized.
- Original floor labels are pseudonymized.
- Team, company, customer, and device labels are removed.
- Floor-plan images with team labels are not included.

## Limitations

- Sound values are calibrated SPL-like dB values from RMS windows, not formally documented LAeq values.
- Environmental sensor channels are not included in this release.
- Topology labels such as walls, doors, and exact open-zone boundaries are not included.
- Event labels are operational validation points, not controlled experiments.
- The data complement standardized room-acoustic measurements; they do not replace them.

## Calibration Validation Data

- `data/processed/calibration_validation/` contains a single continuous, unscripted in-situ co-location session between one Acust device and a calibrated miniDSP UMIK-1 reference measurement microphone, aligned to 1-second bins via cross-correlation (the device log carried only an internal uptime clock, not a wall-clock timestamp).
- This is real, timestamped, dual-instrument data, but it is explicitly one session, one device, one room, with an ambient (not swept-tone or pink-noise) stimulus. It is not a controlled multi-level laboratory calibration campaign and does not establish frequency-response flatness or multi-device inter-unit variation.
- The public `elapsed_seconds` column replaces the original wall-clock timestamp, consistent with this release's exclusion of exact clock times.
- Headline result: Pearson r = 0.87 between the device's calibrated dashboard reading and the UMIK-1 reference; mean bias +8.64 dB (device reads high); RMSE 10.15 dB. An in-sample, session-specific linear correction reduces the residual to 2.40 dB MAE / 3.53 dB RMSE. See `umik1_insitu_summary_by_band_public.csv` for the breakdown by reference SPL band.
