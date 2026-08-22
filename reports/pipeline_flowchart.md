Oxford Battery Degradation Dataset 1
                ↓
        Dataset Understanding
                ↓
       Data Quality Assessment
                ↓
         Data Preprocessing
                ↓
       Exploratory Data Analysis
                ↓
        Feature Preparation
                ↓
       SoH / RUL Construction
                ↓
    Chronological Data Splitting
        Train / Validation / Test
                ↓
      Sequence / Window Creation
                ↓
          Baseline Model
                ↓
        ┌───────┼────────┐
        ↓       ↓        ↓
       LSTM     GRU      TCN
        └───────┼────────┘
                ↓
      Model Comparison & Tuning
                ↓
      Robustness & Error Analysis
                ↓
        Final Model Selection
                ↓
          SoH / RUL Prediction
