# Kubernetes Metrics Data

This directory contains sample Kubernetes metrics data for training and testing machine learning models for failure prediction.

## Dataset Description

The `sample_kubernetes_metrics.csv` file contains examples of Kubernetes metrics data with the following features:

- `timestamp` - Time when the metrics were collected
- `node` - Kubernetes node identifier
- `cpu_usage_percent` - CPU utilization as a percentage
- `memory_usage_percent` - Memory utilization as a percentage
- `disk_usage_percent` - Disk space utilization as a percentage
- `network_receive_bytes` - Network bytes received
- `network_transmit_bytes` - Network bytes transmitted
- `pod_count` - Number of pods running on the node
- `pod_restart_count` - Number of pod restarts
- `pod_pending_count` - Number of pods pending scheduling
- Various node condition indicators (binary values):
  - `node_condition_ready`
  - `node_condition_memory_pressure`
  - `node_condition_disk_pressure`
  - `node_condition_pid_pressure`
  - `node_condition_network_unavailable`
- `cpu_request_percentage` - Percentage of CPU resources requested
- `memory_request_percentage` - Percentage of memory resources requested
- `failure` - Binary target variable (1 = failure, 0 = normal)

## Data Format

CSV format with headers, including both numeric and timestamp data.

## Failure Patterns

The dataset contains examples of various failure patterns, including:

1. CPU exhaustion
2. Memory exhaustion
3. Disk pressure
4. Network issues
5. Node not ready states

## Usage

To use this data for model training, refer to the notebooks in the `/notebooks` directory:

1. Use `data_exploration.ipynb` to explore and visualize the data
2. Use `model_training.ipynb` to train models using this data

## Data Generation

For larger datasets, the `data_generator.py` module can be used to generate synthetic Kubernetes metrics data with configurable parameters:

```python
from data_generator import generate_kubernetes_data

# Generate 5000 samples with 10% failure rate and 30 time steps
data = generate_kubernetes_data(n_samples=5000, failure_rate=0.1, time_steps=30)

# Save to CSV
data.to_csv('data/custom_kubernetes_data.csv', index=False)
```