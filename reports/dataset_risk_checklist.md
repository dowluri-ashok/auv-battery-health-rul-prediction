# Oxford Battery Degradation Dataset 1 — Dataset Risk Checklist

## 1. Missing Data Risk

- [ ] Check whether any time, voltage, charge, or temperature measurements are missing.
- [ ] Check for empty or incomplete characterisation cycles.
- [ ] Check whether all 8 cells contain the expected measurements.
- [ ] Document the amount and location of missing data before applying any imputation.

## 2. Unequal Data Availability

- [ ] Check the number of characterisation cycles available for each cell.
- [ ] Some cells may reach end of life earlier than others.
- [ ] Compare the available cycle history across all 8 cells.
- [ ] Avoid assuming that every cell has the same number of observations.

## 3. Temporal Leakage Risk

- [ ] Preserve the chronological order of battery degradation data.
- [ ] Do not randomly mix early and late degradation measurements between training and testing.
- [ ] Ensure that information from future degradation stages is not used to train the model for earlier stages.
- [ ] Define the train/validation/test strategy before model training.

## 4. Cell-Level Data Leakage Risk

- [ ] Track the cell identity for every observation.
- [ ] Ensure that the selected train/validation/test strategy does not unintentionally leak information between cells.
- [ ] If cross-cell generalization is evaluated, keep test cells completely unseen during training.

## 5. Cycle Ordering Risk

- [ ] Verify that characterisation cycle numbers are correctly ordered.
- [ ] Confirm that labels such as `cyc0100`, `cyc0200`, etc. correspond to the intended degradation stage.
- [ ] Check for duplicate or incorrectly ordered cycle records.

## 6. Measurement and Outlier Risk

- [ ] Check voltage measurements for abnormal values.
- [ ] Check temperature measurements for abnormal values.
- [ ] Check charge measurements for abnormal values.
- [ ] Identify possible sensor or measurement anomalies.
- [ ] Investigate outliers before removing them.

## 7. SoH Definition Risk

- [ ] Define the reference capacity used for SoH calculation.
- [ ] Define how capacity/charge measurements will be converted into SoH.
- [ ] Use a consistent SoH definition across all cells.
- [ ] Document the final SoH formula before model training.

## 8. RUL Definition Risk

- [ ] Define the End-of-Life (EOL) criterion.
- [ ] Define how RUL will be calculated from the available degradation information.
- [ ] Ensure that the same RUL definition is applied consistently across cells.
- [ ] Document the final RUL definition before model training.

## 9. Sampling and Windowing Risk

- [ ] Characterisation measurements are available every 100 drive cycles.
- [ ] Check whether this sampling frequency is sufficient for the planned time-series modelling.
- [ ] Define the input sequence/window length before training.
- [ ] Ensure that windows do not cross inappropriate train/validation/test boundaries.

## 10. Data Processing Leakage

- [ ] Fit normalization/scaling parameters using training data only.
- [ ] Apply the trained transformation to validation and test data.
- [ ] Do not calculate preprocessing statistics using the complete dataset before splitting.

## 11. Dataset Documentation

- [ ] Record the original dataset name and version.
- [ ] Record the source and DOI/citation information.
- [ ] Record all preprocessing steps.
- [ ] Record any removed, transformed, or imputed observations.
- [ ] Keep the raw dataset separate from processed data.

## Overall Risk Status

**Status:** To be completed after inspection of the raw `.mat` file.

The risks listed above are expected risks to be checked during dataset inspection. No data-quality issue should be marked as confirmed until the raw dataset has been examined.
