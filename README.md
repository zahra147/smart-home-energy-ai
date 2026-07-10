# 🏠⚡ Smart Home Energy Analytics

> Intelligent energy consumption prediction and recommendation system for smart homes using real IoT sensor data.

![Python](https://img.shields.io/badge/Python-3.12-blue)
![LightGBM](https://img.shields.io/badge/LightGBM-R²=0.866-green)
![AUC](https://img.shields.io/badge/AUC-0.953-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

---

## 📌 Project Overview

This project develops an end-to-end machine learning pipeline applied to real smart home IoT sensor data. The goal is to analyze, predict, and optimize household energy consumption through multiple ML approaches — from regression to reinforcement learning — with a real-time HMI dashboard output.

---

## 🎯 Key Results

| Component | Method | Result |
|-----------|--------|--------|
| Regression | LightGBM | R² = 0.866 |
| Classification | Random Forest | AUC = 0.953, Acc = 88.93% |
| Clustering | K-Means (k=2) | Silhouette = 0.335 |
| Reinforcement Learning | Q-Learning | Reward +18.8% |
| Recommendation | Dual System (7 categories) | Agreement = 65.7% |

**Key insight:** Adding 7 lag & rolling features boosted R² from 0.718 → 0.866 (+20.6%) — feature engineering outperformed model selection.

---

## 🗂️ Project Structure

```
smart-home-energy-analytics/
│
├── dashboard.ipynb          # Main notebook (full pipeline)
├── requirements.txt
├── README.md
│
├── Data/
│   └── energydata_complete.csv   # UCI smart home dataset
│
├── models/                  # Saved models (see below)
├── outputs/
│   └── hmi_output.json      # QML-ready HMI output
├── figures/                 # All plots
└── smart_home_hmi/
    └── dashboard_app.py     # Interactive Tkinter dashboard
```

---

## 🔬 Pipeline

```
1. Data Loading & Preprocessing
   └── 19,718 rows · 50 features · 10-min intervals

2. Feature Engineering
   └── Lag features (10/20/30/60 min) · Rolling mean/std · Cyclical encoding

3. Regression — 10 models compared
   └── LightGBM (best) · XGBoost · CatBoost · RF · SVR · ...

4. Classification
   └── Random Forest · ROC comparison · Confusion matrix

5. Clustering
   └── K-Means (k=2) · DBSCAN · Hierarchical

6. Dual Recommendation System
   ├── Time-aware RF Classifier (7 categories)
   └── Independent K-Means behavioral recommender

7. Reinforcement Learning
   └── Q-Learning agent · 50 episodes · Learned evening-peak policy

8. HMI Integration
   └── QML-ready JSON · Alert levels · Confidence scores · Q-policy
```

---

## 🚀 Quick Start

```bash
# Clone
git clone https://github.com/YOUR_USERNAME/smart-home-energy-analytics.git
cd smart-home-energy-analytics

# Install dependencies
pip install -r requirements.txt

# Run notebook
jupyter notebook dashboard.ipynb

# Run interactive dashboard
cd smart_home_hmi
python dashboard_app.py
```

---

## 📊 Dashboard

The Tkinter dashboard provides 8 interactive tabs:

| Tab | Content |
|-----|---------|
| Load Data | Dataset overview — distribution, hourly patterns, lag feature preview |
| EDA | Correlation matrix, weekday vs weekend, skewness analysis |
| Models | R² and MAE comparison across 10 models |
| Feature Imp. | LightGBM feature importance (lag features dominate) |
| Residuals | Residual plot and distribution from saved LightGBM model |
| Classification | Confusion matrix + ROC curve |
| Clustering | Silhouette score, PCA scatter, cluster consumption |
| Recommendations | 7-category time-aware recommendation distribution |

---

## 🤖 Models

Large model files are not included in this repo. To regenerate:

```bash
# Run Section 13 in dashboard.ipynb
# Models will be saved to models/
```

Or download from [Releases](https://github.com/YOUR_USERNAME/smart-home-energy-analytics/releases).

---

## 📱 HMI Output

The `outputs/hmi_output.json` file is QML-ready and contains:
- Real-time consumption & alert level
- ML recommendation with confidence score
- LightGBM prediction (next 10 min)
- Q-Learning policy for current state
- Consumption history (last 40 min)
- Cluster assignment & comparison

---

## 📦 Dependencies

```
pandas · numpy · matplotlib · seaborn
scikit-learn · lightgbm · xgboost · catboost
joblib · tkinter
```

---

## 📁 Dataset

**Appliances energy prediction** — UCI Machine Learning Repository  
19,735 instances · 10-minute intervals · 28 features  
[Dataset Link](https://archive.ics.uci.edu/ml/datasets/Appliances+energy+prediction)

---

## 🇩🇪 About

Built as part of a machine learning course project.  
Open to opportunities in **Data Science / ML Engineering** in Germany.

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://linkedin.com/in/YOUR_PROFILE)

---

## 📄 License

MIT License — feel free to use and adapt.
