# Oxford Battery Degradation Dataset 1 — Pipeline Flowchart

## Overall Project Pipeline

```mermaid
flowchart TD
    A[Oxford Battery Degradation Dataset 1] --> B[Dataset Understanding]
    B --> C[Data Quality Assessment]
    C --> D[Data Preprocessing]
    D --> E[Exploratory Data Analysis]
    E --> F[Feature Preparation]
    F --> G[SoH / RUL Target Construction]
    G --> H[Chronological Train / Validation / Test Split]
    H --> I[Sequence / Window Creation]
    I --> J[Baseline Model]

    J --> K[LSTM]
    J --> L[GRU]
    J --> M[TCN]

    K --> N[Model Comparison & Tuning]
    L --> N
    M --> N

    N --> O[Robustness & Error Analysis]
    O --> P[Final Model Selection]
    P --> Q[SoH / RUL Prediction]
