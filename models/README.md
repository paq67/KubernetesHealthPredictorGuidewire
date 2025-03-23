# Model Files

This directory contains trained machine learning models for Kubernetes failure prediction.

## Contents

- `random_forest_model.pkl` - Random Forest Classifier for failure prediction
- `isolation_forest_model.pkl` - Isolation Forest for anomaly detection
- `time_series_model.pkl` - ARIMA model for time series forecasting
- `scaler.pkl` - Feature scaler used for preprocessing new data
- `feature_importance.csv` - Feature importance rankings from the Random Forest model

## Model Training

These models are trained using the notebooks in the `/notebooks` directory. To train your own models with custom parameters, run the `model_training.ipynb` notebook.

## Model Usage

To use these models for prediction:

1. Load the models using joblib:
```python
import joblib
rf_model = joblib.load('models/random_forest_model.pkl')
```

2. Preprocess your data using the same scaling method:
```python
from data_processor import preprocess_data
preprocessed_data, _ = preprocess_data(your_data)
```

3. Use the model to make predictions:
```python
predictions = rf_model.predict(preprocessed_data)
```

## Model Performance

For detailed performance metrics on these models, refer to the `model_evaluation.ipynb` notebook in the `/notebooks` directory.