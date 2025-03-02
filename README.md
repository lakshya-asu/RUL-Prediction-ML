# Remaining Useful Life (RUL) Prediction

## Overview
This project focuses on predicting the Remaining Useful Life (RUL) of engines using machine learning techniques: XGBoost and Long Short-Term Memory (LSTM) neural networks. The goal is to estimate engine lifespan before maintenance or replacement is required, aiding predictive maintenance strategies.

## Data Preprocessing
- **Data Loading**: Sensor measurements from `train_FD003.txt`, `test_FD003.txt`, and `RUL_FD003.txt`.
- **Data Visualization**: Box plots for sensor readings to analyze distributions and detect outliers.
- **RUL Target Processing**: Custom function for early RUL thresholds to enhance realistic predictions.
- **Windowing**: Enables time-series analysis by capturing temporal dependencies.
- **Data Scaling**: StandardScaler applied for feature normalization.

## Model Implementation
### XGBoost Model
- **Hyperparameter Tuning**: Optimized using grid search.
  - `max_depth`: 5
  - `learning_rate`: 0.1
  - `num_rounds`: 110
- **Evaluation Metrics**: RMSE and custom S-score.

### LSTM Model
- **Architecture**:
  - LSTM layers: 64 and 32 units
  - Dense layers: 16 and 1 units
- **Training**:
  - Adam optimizer, Mean Squared Error loss function
  - 100 epochs, batch size: 32, validation split: 0.2

## Results & Evaluation
| Model  | RMSE  | S-score  |
|--------|-------|----------|
| XGBoost | 20.56 | 1814.76 |
| LSTM    | 20.34 | 1776.00 |

LSTM slightly outperforms XGBoost due to its ability to capture long-term dependencies in time-series data.

## Visualizations
- **Sensor Measurement Box Plots**: Identify data distribution patterns.
- **Actual vs Predicted RUL Plots**: Compare model predictions.
- **LSTM Training History**: Monitor training progress and detect overfitting.
- **XGBoost Feature Importance**: Identify critical sensor measurements.

## Discussion & Insights
- **Model Performance**: LSTM captures temporal dependencies better.
- **Feature Importance**: XGBoost highlights key sensors influencing RUL.
- **Practical Applications**: Effective predictive maintenance reduces downtime and costs.

## Future Work
- **Ensemble Models**: Combine XGBoost and LSTM for improved accuracy.
- **Advanced Architectures**: Explore transformers for better performance.
- **Real-time Prediction**: Deploy models for live monitoring.
- **Interpretability**: Enhance model explainability for actionable insights.
- **Generalization**: Test models on diverse machinery for broader applicability.

This project lays a strong foundation for RUL prediction, leveraging machine learning and deep learning to enhance predictive maintenance strategies.
