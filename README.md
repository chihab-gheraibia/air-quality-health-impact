# 🌍 Air Quality & Health Impact Analysis

An end-to-end data science pipeline that analyzes global air quality data, models Air Quality Index (AQI) using machine learning, explains predictions with SHAP, and simulates the health impact of pollution-reduction policies.

## 📊 Project Overview

This project explores a global air pollution dataset (23,463 cities) to understand pollutant distributions, builds a highly accurate Random Forest model to predict AQI, uses SHAP for model explainability, and simulates "what-if" policy scenarios (e.g., cutting PM2.5 by 25%) to estimate their impact on air quality and public health.

## 🔑 Key Results

| Metric | Value |
|---|---|
| Dataset size | 23,463 rows |
| Features used | 9 |
| MAE | 0.11 AQI points |
| RMSE | 1.52 AQI points |
| R² (test set) | 0.9993 |
| R² (5-fold CV) | 0.9994 ± 0.0003 |
| Top predictive feature | `pollutant_spread` (importance: 0.802) |
| Biggest policy lever | 25% cut in PM2.5 → −1.06 avg AQI |

## 🗂️ Repository Structure

```
air-quality-health-impact/
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   └── AIR_QUALITY_HEALTH_IMPACT.ipynb   # Full analysis pipeline
├── data/
│   ├── global_air_pollution_data.csv     # Raw dataset
│   └── city_health_risk_report.csv       # Model output: per-city risk scores
├── outputs/
│   ├── eda_01_aqi_distribution.png
│   ├── eda_02_correlation.png
│   ├── eda_03_country_rankings.png
│   ├── eda_04_pollutant_breakdown.png
│   ├── eda_05_world_aqi_map.html
│   ├── model_01_actual_vs_predicted.png
│   ├── model_02_residuals.png
│   ├── model_03_feature_importance.png
│   ├── shap_01_summary_beeswarm.png
│   ├── shap_02_bar.png
│   ├── shap_03_dependence_pm25.png
│   ├── shap_04_waterfall_single.png
│   └── policy_simulator.png
└── pipeline_summary_report.txt
```

## 🔬 Pipeline Stages

1. **Exploratory Data Analysis** — AQI distribution, correlation matrix, country rankings, pollutant breakdown by category, world AQI map.
2. **Feature Engineering** — `pollutant_spread`, `mean_pollutant_aqi`, `pm25_ratio`, country encoding.
3. **Modeling** — Random Forest Regressor predicting AQI (R² = 0.9993 on held-out test data, validated with 5-fold cross-validation).
4. **Model Diagnostics** — Actual vs. predicted plots, residual analysis.
5. **Explainability (SHAP)** — Beeswarm summary, mean |SHAP value| bar chart, PM2.5 dependence plot, waterfall plot for the worst-predicted case.
6. **Policy Simulation** — Estimates the AQI reduction from hypothetical cuts to each pollutant, identifying PM2.5 reduction as the highest-leverage intervention.
7. **City Health Risk Report** — Exported per-city risk scores (`city_health_risk_report.csv`).

## 🛠️ Tech Stack

- **Data processing:** pandas, numpy
- **Visualization:** matplotlib, seaborn, plotly
- **Modeling:** scikit-learn (Random Forest)
- **Explainability:** SHAP

## 🚀 Getting Started

```bash
git clone https://github.com/<your-username>/air-quality-health-impact.git
cd air-quality-health-impact
pip install -r requirements.txt
jupyter notebook notebooks/AIR_QUALITY_HEALTH_IMPACT.ipynb
```

## 📈 Sample Visualizations

See the `outputs/` folder for all charts, including the AQI distribution, feature correlation matrix, country rankings, SHAP explainability plots, and the policy simulator results.

## 📄 License

This project is open-sourced for educational and portfolio purposes.
