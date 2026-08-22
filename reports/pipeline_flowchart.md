# Oxford Battery RUL Prediction — Pipeline Flowchart

## Overall Pipeline

```text
Oxford Battery Degradation Dataset
                ↓
        Data Loading
                ↓
       Data Validation
                ↓
       Data Cleaning
                ↓
     Feature Extraction
                ↓
      Feature Engineering
                ↓
       Sequence Creation
                ↓
     Train / Validation / Test Split
                ↓
        Model Training
                ↓
       Model Evaluation
                ↓
       RUL Prediction
                ↓
     Results & Visualization
