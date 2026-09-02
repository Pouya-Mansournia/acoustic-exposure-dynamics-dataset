# Privacy and Limitations

## Privacy transformations

- Raw audio was not stored and is not included.
- Raw deployment logs are not included.
- Row-level calendar timestamps and clock times are removed.
- Hardware IDs are removed; nodes use `N01` through `N10` or other public pseudonyms.
- Original floor, team, company, and customer labels are removed.
- Labeled source floor plans are not included.

## Measurement limitations

- Values are firmware-reported SPL-like dB, not formal LAeq measurements.
- Nodes were not tested for IEC 61672 class conformity.
- Controlled level, frequency-response, A-weighting, drift, placement, and full
  numerical uncertainty evidence is not available.
- Operational events are observations, not controlled or replicated interventions.
- The dataset complements standardized measurements; it does not replace them.

## Reference comparisons

The single-device and ten-device UMIK-1 comparisons are uncontrolled,
ambient-stimulus sessions requiring post-hoc alignment. The single-device
correction is in-sample. The chronological holdout remains within the same
ambient session, and the historical-correction transfer does not remove
device-to-device spread. These analyses bound interpretation and motivate a
controlled campaign; they are not formal validation.
