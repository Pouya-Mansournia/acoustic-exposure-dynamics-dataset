# Release Notes

## v1.1.0 - draft, not yet published

Adds real calibration-validation evidence; not yet tagged on GitHub or archived on Zenodo.

### Added

- `data/processed/calibration_validation/umik1_insitu_comparison_1s_public.csv`: 1-second-bin aligned comparison between one Acust device and a calibrated UMIK-1 reference microphone over a single continuous, unscripted co-location session (1,845 samples). Wall-clock timestamps replaced with `elapsed_seconds` per this release's privacy policy.
- `data/processed/calibration_validation/umik1_insitu_summary_by_band_public.csv`: bias/MAE/RMSE by UMIK-1 reference SPL band.
- `figures/manuscript/fig_umik1_insitu_comparison.png`: time-aligned series and device-vs-reference scatter for the session above.
- `figures/manuscript/fig_calibration_engine_pipeline.png`: diagram of the redesigned firmware acoustic-processing pipeline (implemented, not yet physically validated at the fleet level; disclosed as such).
- New `calibration_validation` block in `data/metadata/public_manifest.json` and matching entries in `data/metadata/data_dictionary.md` and `docs/privacy_and_limitations.md`.

### Headline result

Pearson r = 0.87 between the device's calibrated dashboard reading and the UMIK-1 reference; mean bias +8.64 dB (device reads high); RMSE 10.15 dB. An in-sample, session-specific linear correction reduces the residual to 2.40 dB MAE / 3.53 dB RMSE. Scoped explicitly as one device, one room, one session, ambient (not swept-tone) stimulus — not a controlled multi-level laboratory calibration campaign.

## v1.0.0 - 2026-07-23

Initial public scholarly dataset release prepared for GitHub and Zenodo.

### Included

- Anonymized aggregate feature tables for the main multi-floor deployment (`Deployment_A`).
- Anonymized aggregate validation tables for the independent validation deployment (`Deployment_B`).
- Cross-deployment replication summaries.
- Public metadata manifest, data dictionary, and pseudonymized sensor keys.
- Anonymized manuscript figures.
- Privacy and methodology notes.
- Machine-readable citation metadata in `CITATION.cff`.
- Zenodo metadata in `.zenodo.json`.

### Excluded

- Raw audio.
- Raw high-frequency sound logs.
- Exact calendar dates, clock times, weekday labels, customer names, team labels, original floor labels, and labeled floor-plan images.
- Private raw data, customer metadata, and non-public Acust.ai/X-Robotiics deployment materials.

### License

The public aggregate dataset, documentation, and figures are released under CC BY 4.0. Private raw data and non-public deployment materials are outside the scope of this license.

### DOI

DOI: [10.5281/zenodo.21503880](https://doi.org/10.5281/zenodo.21503880)

GitHub release: <https://github.com/Pouya-Mansournia/acoustic-exposure-dynamics-dataset/releases/tag/v1.0.0>
