# 🇩🇪 Supply–Demand & Pricing Modelling of German Gas & LNG  

**Author:** Mohit Kumar  
**Tools:** Python | Machine Learning | Energy Economics | Data Integration | API Automation  

---

## 🧩 Project Overview  

This project develops a **monthly supply–demand and pricing model** for Germany’s **natural gas and LNG market**, combining open data sources and machine learning to explain and forecast price movements.  

It integrates multiple market components — **imports, consumption, storage, global prices, and LNG supply trends** — to capture the structural drivers of Germany’s gas balance post-2020.  

The analysis includes:
- Data integration from **Eurostat**, **AGSI+**, **EIA**, and **Investing.com**
- Forecasting of **TTF price dynamics** using **regression and tree-based ML models**
- **Scenario simulations** (e.g., ±20% import momentum shocks)
- **Feature interpretability** using **SHAP values**
- Export-ready insights for reporting and visualization  

---

## ⚙️ Data Sources  

| Source | Description | Access Method |
|--------|--------------|----------------|
| Eurostat | Monthly imports & consumption of natural gas | REST API |
| AGSI+ | LNG terminal send-out & gas storage levels | API |
| EIA | US LNG exports to Europe | API |
| Investing.com | TTF, JKM, Brent, Henry Hub prices | Manual CSV download |

All data are aggregated and resampled to **monthly frequency** starting **April 2020**.

---

## 📊 Key Features  

### 🔹 Market Fundamentals  
- **Gas_Imports_momentum_3m** – 3-month rolling growth rate of imports  
- **Storage_Fill_Rate** – AGSI+ monthly storage utilization  
- **Brent_Crude_Price**, **HenryHub_Price**, **JKM_Price** – global benchmarks  
- **Temperature_Anomaly** – weather-driven demand factor  

### 🔹 Derived Features  
- Lagged regressors (1–3 months)
- Rolling means and momentum terms
- Normalized growth ratios for trend comparison  

---

## 🔍 Modelling Approach  

| Step | Description |
|------|--------------|
| **1. Preprocessing** | Merge and clean all datasets, handle missing values, convert to monthly time series |
| **2. Feature Engineering** | Construct lags, moving averages, and relative indicators |
| **3. Model Training** | Fit ML models (Linear Regression, Random Forest, XGBoost) |
| **4. Forecasting** | Evaluate models on out-of-sample period using MAE & RMSE |
| **5. Causality & Elasticity Tests** | Granger causality, elasticity coefficients, and lag response analysis |
| **6. Interpretability** | SHAP value plots for feature-level impact |
| **7. Scenario Simulation** | ±20% shocks to import momentum and impact on price forecast |

---

## 🧮 Scenario & Sensitivity  

The model simulates **import shocks** to assess price sensitivity:  
- `+20%` import momentum → **downward pressure on TTF prices**  
- `−20%` import momentum → **upward price pressure**  

Results are exported to:  

Scenario_Simulation_Results.csv
Feature_Importance_SHAP.png


---

## 🧠 Interpretability (SHAP)  

Feature importance and SHAP analysis reveal:
- **Storage_Fill_Rate** and **Imports_Momentum** as the most influential drivers of TTF  
- Oil-linked benchmarks (Brent, JKM) contribute to longer-lag structural trends  
- Weather variables (Temperature_Anomaly) show moderate short-term elasticity  

![](Feature_Importance_SHAP.png)

---


---

## 🧠 Interpretability (SHAP)  

Feature importance and SHAP analysis reveal:
- **Storage_Fill_Rate** and **Imports_Momentum** as the most influential drivers of TTF  
- Oil-linked benchmarks (Brent, JKM) contribute to longer-lag structural trends  
- Weather variables (Temperature_Anomaly) show moderate short-term elasticity  

🧾 License

This project is licensed under the MIT License — see the LICENSE
 file for details.

📬 Contact

Mohit Kumar
📍 Noida, India
✉️ mohitkr.h@gmail.com

🔗 LinkedIn
 | GitHub

An integrated view of LNG market dynamics — where imports, storage, and global benchmarks converge to shape Europe’s energy pricing.
