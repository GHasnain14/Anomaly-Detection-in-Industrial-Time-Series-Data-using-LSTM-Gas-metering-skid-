# 🚨 Anomaly Detection in Fiscal Gas Metering Data (LSTM)

[![Python](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)](https://www.tensorflow.org/)
[![License](https://img.shields.io/badge/license-MIT-green)](LICENSE)

This repository provides a complete pipeline for **detecting anomalies in fiscal gas metering systems**, with a focus on three critical parameters: **Flow, Pressure, and Temperature**.

It leverages a **Long Short-Term Memory (LSTM) Autoencoder** to learn normal operating behavior from historical data. Once trained, the model can identify deviations as **potential anomalies** helping operators prevent costly errors in **custody transfer applications**.

 **Why it matters**: In fiscal gas metering, even a tiny error in flow or compensation measurements can result in **multi-million dollar financial losses**. Early detection of anomalies is essential for maintaining accuracy, reliability, and compliance with AGA/API/ISO standards.

---

##  Key Features

*  **Multivariate Time-Series Support**: Works with Flow, Pressure, and Temperature.
*  **LSTM Autoencoder**: Learns sequential dependencies in operational data.
*  **Anomaly Detection**: Flags abnormal deviations using prediction error thresholds.
*  **Built-In Visualizations**:

  * Correlation matrix of features
  * Error distribution plots
  * Time-series anomaly analysis per feature

---

## 📂 Repository Structure

```
├── anomaly_detection.py                 # Main script
├── synthetic_fiscal_metering_data.xlsx  # Example dataset (replace with your own)
├── requirements.txt                     # Dependencies
├── Plots/                               # Auto-generated results
│   ├── 00_correlation_matrix.png
│   ├── prediction_error_distribution.png
│   ├── 04_Flow_analysis.png
│   ├── 04_Pressure_analysis.png
│   └── 04_Temperature_analysis.png
└── README.md
```

---

##  Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/yourusername/fiscal-metering-anomaly-detection.git
cd fiscal-metering-anomaly-detection
pip install -r requirements.txt
```

---

##  Usage

1. Place your dataset (`.xlsx`) in the project folder.

   * Required columns: **Timestamp, Flow, Pressure, Temperature**

2. Update the `CONFIG` dictionary inside `anomaly_detection.py` with your file name and parameters:

```python
CONFIG = {
    "file_path": "synthetic_fiscal_metering_data.xlsx",
    "features": ["Flow", "Pressure", "Temperature"],
    "timestamp_col": "Timestamp",
    "time_steps": 60,
    "epochs": 50,
    "batch_size": 32,
    ...
}
```

3. Run the script:

```bash
python anomaly_detection.py
```

4. Check the **Plots/** directory for results.

---

## 📊 Outputs

The script generates professional visualizations for easier interpretation:

* **Correlation Matrix** – shows relationships between Flow, Pressure, and Temperature.
* **Error Distribution** – separates normal vs anomalous data points.
* **Per-Feature Analysis** – time-series plots with detected anomalies highlighted.

Example anomaly plot:

<img width="4500" height="3000" alt="01_Flow_analysis" src="https://github.com/user-attachments/assets/96e55368-0180-495c-b161-9d3453867fb8" />


---

##  Requirements

```
pandas
numpy
matplotlib
seaborn
scikit-learn
tensorflow
openpyxl
```

---

## 👤 Author

**Ghulam Hasnain**
Mechatronics & Control Engineer | Industrial Automation & Instrumentation | AI for Oil & Gas

---
