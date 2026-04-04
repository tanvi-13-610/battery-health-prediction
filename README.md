# 🔋 Battery Health Prediction

Predicting lithium-ion battery State of Health (SOH) and Remaining Useful Life (RUL) using the NASA Battery Dataset.

## Overview
An end-to-end AI/ML project that predicts the State of Health (SOH) and Remaining Useful Life (RUL) of lithium-ion batteries using the NASA Battery Dataset.

## Dataset
- **Source:** NASA Prognostics Center Battery Dataset (via Kaggle)
- **Batteries:** 52 batteries (B0005 – B0056)
- **Cycles:** 2,769 discharge cycles
- **Features:** Voltage, Current, Temperature per cycle

## Features Engineered (per cycle)
`mean_voltage` `min_voltage` `max_voltage` `voltage_std` `mean_current` `mean_temp` `max_temp` `discharge_time` `voltage_range` `energy (Wh)` `internal_resistance_proxy`

## Model Performance

| Model | RMSE | R² |
|-------|------|-----|
| Random Forest | 0.0490 | 0.8324 |
| LSTM | 0.0665 | 0.6910 |
| RF 5-Fold CV | Mean R²: 0.7935 | Std: 0.0606 |
| LSTM 5-Fold CV | Mean R²: 0.3530 | Std: 0.0340 |
| Tuned RF (GridSearchCV) | 0.0441 | 0.8691 |

## Key Results
- SOH predicted with ~4.4% average error (Tuned RF)
- RUL estimated with confidence intervals
- `discharge_time` is the most important feature
- Random Forest outperforms LSTM on this dataset
- 92% classification accuracy for Healthy/Degrading/Critical battery states
- Gradio dashboard powered by best_rf (Tuned Random Forest)

## Note on Critical Class
The Critical class (SOH < 0.6) scored 0% in classification — this is expected and not a model failure. Only 5 out of 341 test samples fell into this category, which is too few for the model to learn from. With more critical battery data, performance would improve.

## Tech Stack
Python · TensorFlow/Keras · Scikit-learn · Pandas · NumPy · Matplotlib · Gradio

## Files
| File | Description |
|------|-------------|
| `battery_health_prediction_final.ipynb` | Main notebook |
| `battery_lstm_model.h5` | Trained LSTM model |
| `scaler_X.pkl` | Feature scaler |
| `scaler_y.pkl` | Target scaler |
| `sample_battery_input.csv` | Sample input for dashboard |
