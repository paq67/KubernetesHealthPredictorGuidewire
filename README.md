# Kubernetes Failure Prediction

A machine learning application for predictive Kubernetes cluster health monitoring and failure prevention.

## Project Structure

📁 `/notebooks` – Code for data collection, model training,  and evaluation
- `data_exploration.ipynb` - Exploratory analysis of Kubernetes metrics data
- `model_training.ipynb` - Training various ML models for failure prediction
- `model_evaluation.ipynb` - Evaluation of model performance and visualizations

📁 `/models` – Trained model files
- `random_forest_model.pkl` - Classification model for failure prediction
- `isolation_forest_model.pkl` - Anomaly detection model
- `time_series_model.pkl` - ARIMA forecasting model

📁 `/data` – Sample data and datasets
- `sample_kubernetes_metrics.csv` - Example Kubernetes metrics

📁 `/docs` – Complete documentation
- Detailed README.md with project overview, methods, and technical details

## Main Technologies

- Streamlit for the web interface
- Scikit-learn for machine learning models
- Pandas and NumPy for data processing
- Plotly and Matplotlib for visualization
- Statsmodels for time   series analysis

## Quick Start

To run the application:

```bash
# Install dependencies
pip install -r requirements.txt

# Launch the application
streamlit run app.py
```

## Documentation

For detailed documentation, please refer   to the [docs/README.md](docs/README.md) file.

