# Oxford Battery Degradation Dataset 1 — Pipeline Flowchart

## 1. Overall Project Pipeline

```text
Oxford Battery Degradation Dataset 1
                ↓
        Raw MATLAB Dataset
                ↓
        Data Loading & Parsing
                ↓
        Dataset Structure Inspection
                ↓
        Data Quality Checks
                ↓
     Missing Data / Cycle Checks
                ↓
          Preprocessing
                ↓
      Feature & Target Preparation
                ↓
     Chronological Data Splitting
                ↓
      Sequence / Window Creation
                ↓
          Baseline Model
                ↓
       Deep Learning Models
        ┌───────┼────────┐
        ↓       ↓        ↓
       LSTM     GRU      TCN
        └───────┼────────┘
                ↓
       Model Evaluation
                ↓
 MAE | RMSE | MAPE | R²
                ↓
 Training Time | Inference Time
                ↓
          Model Comparison
                ↓
       Final RUL Prediction
