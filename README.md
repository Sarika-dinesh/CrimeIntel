# CrimeIntel 🕵️‍♀️📊  
**Predicting and Preventing Urban Crime Using Data-Driven Insights**

CrimeIntel is a data-driven analytics framework designed to analyze, predict, and visualize urban crime patterns using large-scale crime data from the **Los Angeles Police Department (LAPD)**. The project integrates classical machine learning, deep learning, and spatio-temporal modeling to move crime analysis from *reactive* to *proactive* decision-making.

---

## 🚀 Project Objectives
CrimeIntel addresses the following research questions:

1. **Crime Type Prediction**  
   Predict major crime categories (Theft, Assault, Burglary, Others) using incident-level metadata.

2. **Crime Severity Classification**  
   Classify crimes as *violent* or *non-violent* using text-driven and weapon-based indicators.

3. **Crime Pattern Anomaly Detection**  
   Detect unusual crime patterns across space and time using unsupervised learning.

4. **Crime Hotspot Prediction**  
   Forecast future spatial crime hotspots using deep spatio-temporal neural networks.

---

## 📂 Dataset
- **Source:** Los Angeles Police Department (LAPD) Open Crime Data  
- **Time Span:** January 2020 – Present  
- **Scale:** 1M+ crime incidents  
- **Features:** Temporal, spatial (lat/long), victim info, weapon type, premises, crime descriptions

---

## 🧠 Methodology Overview

### 1. Crime Type Prediction
- **Models:** XGBoost, Random Forest  
- **Techniques:**  
  - Keyword-based hierarchical labeling  
  - Temporal train/validation/test split (pre-2023 / 2023 / 2024+)  
  - Class imbalance handling via weighted loss  
- **Best Model:** XGBoost (Macro F1 ≈ 0.73)

### 2. Crime Severity Classification
- **Task:** Violent vs Non-Violent classification  
- **Models:** LASSO, Ridge, Random Forest, HistGradientBoosting  
- **Labeling:** Hybrid rule-based approach using crime descriptions + weapon usage  
- **Best Models:** Random Forest (best recall), HistGradientBoosting (best AUC ≈ 0.87)

### 3. Anomaly Detection
- **Approach:** PCA-based unsupervised anomaly detection  
- **Goal:** Identify rare or irregular crime patterns  
- **Output:** Reconstruction error scores with percentile-based anomaly thresholds

### 4. Crime Hotspot Prediction
- **Models:** CNN-LSTM, ConvLSTM  
- **Representation:** Weekly spatio-temporal grids (≈5.5 km resolution)  
- **Best Model:** ConvLSTM  
  - Lower MAE & RMSE  
  - Higher R² (≈ 0.89)  
- **Visualization:** Heatmaps + Google Maps hotspot overlays

---

## 📊 Key Results
- Ensemble tree models outperform linear baselines for both crime type and severity prediction  
- PCA effectively isolates rare and anomalous crime patterns  
- **ConvLSTM** consistently outperforms CNN-LSTM for hotspot forecasting, confirming the benefit of joint spatial-temporal modeling

---

## 🛠️ Tech Stack
- **Languages:** Python  
- **Libraries:**  
  - Data: Pandas, NumPy, Scikit-learn  
  - ML: XGBoost, RandomForest, HistGradientBoosting  
  - DL: TensorFlow / Keras  
  - Visualization: Matplotlib, Seaborn, Google Maps API  
- **Optimization:** Optuna, GridSearchCV  

---

## Disclaimer
This project uses publicly available crime data and is intended **for academic and research purposes only**. Predictions should not be interpreted as deterministic or used as sole inputs for real-world law enforcement decisions.

---

## Future Work
- Transformer and Graph Neural Network extensions  
- Cross-city generalization  
- Deployment-ready dashboards with real-time alerts  

---

⭐ If you find this project useful, feel free to star the repository!
