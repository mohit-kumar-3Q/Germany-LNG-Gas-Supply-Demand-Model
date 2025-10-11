# Gas Supply–Demand Modeling – German Gas & LNG Market ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Author:** Mohit Kumar  
**Email:** mohitkr.h@gmail.com  

---

## Project Overview

This project develops a **monthly supply–demand model** for Germany’s natural gas and LNG market. It integrates multiple open data sources into a single analytical framework to understand how supply fundamentals, storage, and global price benchmarks influence the German gas balance.

The project focuses on **Net Supply Position (NSP)** as the target variable and uses machine learning, statistical tests, and scenario simulations to quantify system behavior and resilience under various shocks.

**Key goals:**
- Build a unified monthly dataset of Germany’s gas supply, demand, and storage.
- Integrate LNG and benchmark price data (TTF, JKM, Henry Hub, Brent).
- Analyze correlations, causal relationships, and elasticities.
- Develop baseline ML models to explain and forecast demand and supply trends.
- Conduct scenario simulations and SHAP explainability for risk insights.

---

## Data Sources

- **Eurostat:** Gas imports, consumption, production, and Heating Degree Days (HDD)  
- **AGSI:** LNG terminal flows and storage levels  
- **EIA:** US LNG exports, Henry Hub prices  
- **Global Price Benchmarks:** TTF, JKM, Brent   

**Time Period:** October 2017 – March 2025 (monthly frequency)  
**Dataset Size:** 90 months, 24 reduced features (19 lag/rolling + 5 seasonal)  

---

## Methodology

1. **Data Ingestion & Cleaning:** Automated and manual harmonization of multiple sources into a consistent monthly time series.  
2. **Exploratory Data Analysis (EDA):** Visualizations, correlations, seasonality analysis, and data distribution checks.  
3. **Statistical Testing:** Granger causality, regression analysis, and market elasticity testing to understand key drivers.  
4. **Feature Engineering:** Creation of lag features (1, 6, 12 months), rolling averages, and seasonal indicators.  
5. **ML Modeling Pipeline:**  
   - **Baseline models:** Random Forest, Gradient Boosting, XGBoost, LightGBM  
   - **Performance Highlights:**  
     - Random Forest: Test R² = 0.562, MAE ≈ 558  
     - Seasonal Naive: Test R² = 0.685, MAE ≈ 528  
     - Ensemble (Seasonal Naive + RF): Test R² = 0.732, MAE = 494.64  
   - **SHAP Explainability & Scenario Analysis:** Heating_Degree_Days_lag12 and Gas_Imports_lag12 are top predictors.  
6. **Scenario Simulation:**  
   - Extreme cold winter (+50% HDD) → NSP impact: –0.4% avg, range –168 to +35 units  
   - Major gas price shock (+100%) → NSP impact: +0.2% avg, range –6 to +42 units  
   - Production crisis (-30% Indigenous) → NSP impact: +0.1% avg, range –5 to +18 units  
   - Import crisis (-50% Gas Imports) → NSP impact: +0.2% avg, range –17 to +58 units  

---

## Key Findings

- **Seasonal Dominance:** Heating cycles strongly drive German gas demand; storage withdrawals align with cold periods.  
- **LNG Flexibility:** Imports increase when storage levels fall; system buffers against supply shocks.  
- **Global Price Influence:** TTF, JKM, and HH spreads have moderate impact on supply-demand balances.  
- **Feature Importance (Top 5):**  
  1. Heating_Degree_Days_lag12 → 0.262  
  2. Gas_Imports_lag12 → 0.175  
  3. Heating_Degree_Days_lag6 → 0.127  
  4. Heating_Degree_Days_lag1 → 0.066  
  5. Gas_Imports_lag1 → 0.064  
- **Model Insights:** Ensemble model combines seasonal patterns with lagged ML features, capturing 73% variance in NSP.  
- **Scenario Impacts:** System demonstrates resilience to shocks; lagged features limit immediate sensitivity but ensure stable predictions.  

---

## Usage

Clone the repository and open the Jupyter notebook to follow the full supply–demand modeling workflow:

```bash
git clone https://github.com/mohit-kumar-3Q/german-gas-lng-market-model.git
