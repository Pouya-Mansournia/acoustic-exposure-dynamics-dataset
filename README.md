# Acoustic Exposure Dynamics Dataset

An anonymized collection of long-term dB-only office sound-level feature tables and analysis outputs for studying privacy-preserving acoustic exposure dynamics in occupied buildings.

This repository supports research on long-term spatiotemporal sound-level behavior from distributed passive office monitoring. It intentionally does not include raw audio, speech content, raw high-frequency logs, customer/team labels, exact calendar dates, clock times, or floor-plan images with identifying labels.

## What This Repository Contains

- Anonymized sensor-level, period-level, floor-level, pairwise, and operational-effect feature tables.
- Public figures derived from anonymized aggregate data.
- Public metadata describing the release structure and privacy transformations.
- A lightweight data dictionary and methodology notes.

## What This Repository Does Not Contain

- Raw audio.
- Raw sound logs.
- Exact calendar dates, weekday labels, or clock times.
- Names of teams, people, customers, or exact floor-plan labels.
- RT60, T20/T30, impulse responses, or sound-source labels.
- CO2, temperature, humidity, or light measurements.

## Underlying Study Summary

- Underlying raw records: 185,140,775 calibrated dB-like sound-level records.
- Public sensors: 56 pseudonymized nodes (`S001`, `S002`, ...).
- Public floors: 5 pseudonymized floors (`Floor_A`, ...).
- Monitoring duration: one continuous deployment month.
- Signal: calibrated SPL-like dB values derived from 5 ms RMS windows.
- Raw audio: not stored.

## Key Aggregate Findings

- Broad remote-work periods reduced mean sound levels by about 2.76 dB relative to normal workdays.
- Low-attendance periods reduced mean sound levels by about 6.27 dB relative to normal workdays.
- The main activity window was about 5.72 dB above other periods.
- Normal-workday floor means differed substantially across anonymized floors.
- Approximate geometric distance alone weakly explained pairwise daily synchrony.

These findings should be interpreted as long-term acoustic exposure dynamics, not occupancy counts or source classification.

## Repository Structure

```text
data/
  metadata/
    public_manifest.json
    sensor_key_public.csv
    data_dictionary.md
  processed/
    sensor_summary_features_public.csv
    period_sensor_features_public.csv
    pairwise_sensor_metrics_public.csv
    ...
figures/
  activity_window_contrast_public.png
  correlation_vs_distance_public.png
  normal_workday_floor_means_public.png
  operational_event_effects_public.png
docs/
  methodology_notes.md
  privacy_and_limitations.md
```

## Scientific Boundaries

This dataset contains sound-level aggregates and features, not raw audio. Therefore it cannot support claims about:

- RT60, T20, T30, or room impulse responses.
- Acoustic absorption coefficients or acoustic treatment quantities.
- Speech content, sound-source identity, or source classification.
- Exact occupancy counts.
- Physical sound propagation time between nodes.

## Suggested Citation

Mansournia, P. et al. Acoustic Exposure Dynamics Dataset: Anonymized long-term dB-only office sound-level features for privacy-preserving acoustic monitoring research. GitHub repository.

## License

No explicit reuse license has been granted yet. Please contact the repository owner before using the data in publications or derivative datasets.
