# Oxford Battery Degradation Dataset 1 — Dataset Schema

## 1. Dataset Overview

- Dataset: Oxford Battery Degradation Dataset 1
- Number of cells: 8
- Cell type: Kokam SLPB533459H4 lithium-ion pouch cells
- Nominal capacity: 740 mAh
- Test temperature: 40 °C
- Characterisation measurements: Every 100 drive cycles

## 2. Raw Dataset File

Primary dataset file:

`Oxford_Battery_Degradation_Dataset_1.mat`

The dataset is stored in MATLAB `.mat` format.

## 3. Dataset Structure

The dataset follows a hierarchical structure:

Cell
→ Characterisation cycle number
→ C1 charge / C1 discharge / pseudo-OCV charge / pseudo-OCV discharge
→ Time / Voltage / Charge / Temperature

### Layer 1 — Cells

Cells 1 to 8.

### Layer 2 — Characterisation Cycle

Characterisation measurements are identified by cycle number, for example:

`cyc0100`

which represents characterisation data after 100 drive cycles.

### Layer 3 — Characterisation Tests

Each characterisation cycle contains:

- C1 charge (`C1ch`)
- C1 discharge (`C1dc`)
- Pseudo-OCV charge (`OCVch`)
- Pseudo-OCV discharge (`OCVdc`)

### Layer 4 — Measurements

Each test contains:

- `t` — Time (seconds)
- `v` — Voltage (Volts)
- `q` — Charge (mAh)
- `T` — Temperature (°C)

## 4. Project-Level Data Requirements

The project will investigate battery health and Remaining Useful Life (RUL) prediction using the available degradation measurements.

Potential input variables include:

- Voltage
- Charge
- Temperature
- Cycle/characterisation-cycle information

The exact feature set will be finalized after inspecting the raw `.mat` file.

## 5. Target Variables

### State of Health (SoH)

SoH definition will be finalized after inspecting the available capacity/charge measurements and establishing the project reference capacity.

### Remaining Useful Life (RUL)

RUL definition and End-of-Life (EOL) criterion will be finalized during the methodology design stage.

## 6. Data Processing Requirements

Before model development, the dataset should be checked for:

- Missing measurements
- Invalid or abnormal values
- Duplicate records
- Correct cycle ordering
- Cell-wise data consistency
- Temporal data leakage
- Cell-level data leakage

The train/validation/test splitting strategy must preserve the temporal nature of battery degradation data.
