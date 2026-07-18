# Acoustic Exposure Dynamics Dataset

[![License: CC BY 4.0](https://img.shields.io/badge/License-CC_BY_4.0-lightgrey.svg)](LICENSE.md)

An anonymized companion dataset for studying privacy-preserving, long-term dB-only acoustic exposure dynamics in occupied office deployments.

This repository contains aggregate feature tables, mixed-effects model outputs, cross-deployment validation summaries, and publication figures. It does not contain raw audio, raw high-frequency logs, exact calendar dates, clock times, customer names, team labels, original floor labels, or labeled floor-plan images.

## Dataset Snapshot

| Item | Public description |
|---|---|
| Main deployment | `Deployment_A`: 56 pseudonymized nodes across five anonymized floors |
| Validation deployment | `Deployment_B`: 13 pseudonymized nodes on one anonymized floor |
| Underlying records | 185,140,775 in Deployment A; 24,393,582 in Deployment B |
| Signal | Calibrated SPL-like dB values derived from 5 ms RMS windows |
| Raw audio | Not stored and not released |
| Public data level | Aggregate features, summaries, model outputs, and figures |

`SPL-like` means device-calibrated sound-level values derived from deployed firmware. It should not be interpreted as IEC-certified sound-level-meter output.

## Pilot Overview

![Privacy-preserving monitoring architecture](figures/manuscript/fig_system_architecture.png)

![Cross-deployment replication summary](figures/manuscript/fig_cross_building_replication.png)

## What Is Included

- `data/processed/main_deployment/`: Deployment A aggregate features, pairwise metrics, mixed-effects outputs, and sensitivity analyses.
- `data/processed/validation_deployment/`: Deployment B aggregate validation features.
- `data/processed/cross_deployment/`: cross-deployment replication summaries.
- `data/metadata/`: public manifest, data dictionary, and pseudonymized sensor keys.
- `figures/manuscript/`: publication-ready anonymized figures.
- `docs/`: methodology notes and privacy limitations.

## Key Use Cases

- Long-term office acoustic exposure analysis.
- Privacy-preserving acoustic monitoring research.
- Operational-regime comparison across workday, closed-day, and activity-window conditions.
- Testing whether average dB hides variability, high-exposure share, and quiet-period differences.
- Reproducing public model and sensitivity outputs from the manuscript.

## Scientific Boundaries

This dataset supports operational acoustic observability, not standardized room-acoustic characterization. It cannot support claims about RT60, T20/T30, room impulse responses, absorption coefficients, speech content, sound-source identity, exact occupancy counts, or physical propagation time between nodes.

Event-level categories are operational case observations rather than statistically replicated interventions.

## Repository Structure

```text
data/
  metadata/
  processed/
    main_deployment/
    validation_deployment/
    cross_deployment/
figures/
  manuscript/
docs/
```

## Citation

If you use this dataset, cite this repository and the associated manuscript when available:

> Mansournia, P. et al. Acoustic Exposure Dynamics Dataset: Anonymized long-term dB-only office sound-level features for privacy-preserving acoustic monitoring research.

See [`CITATION.cff`](CITATION.cff) for machine-readable citation metadata.

## License

The public aggregate dataset and documentation are released under the [Creative Commons Attribution 4.0 International License](LICENSE.md).

Private raw data, raw logs, customer metadata, and any non-public deployment materials are not included in this release and are not licensed by this repository.
