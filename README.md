# auv-battery-health-rul-prediction

Deep Learning for AUV Battery Health Monitoring and RUL Prediction

## Project Pipeline

```mermaid
flowchart TD
    A["AUV Battery Dataset"] --> B["Data Collection"]
    B --> C["Data Preprocessing"]
    C --> D["Exploratory Data Analysis"]
    D --> E["Feature Engineering"]
    E --> F["Train / Validation / Test Split"]
    F --> G["Deep Learning Model"]
    G --> H["SOH Estimation"]
    H --> I["RUL Prediction"]
    I --> J["Model Evaluation"]
    J --> K["Results & Visualization"]
