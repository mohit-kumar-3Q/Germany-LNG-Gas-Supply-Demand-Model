# Gas Supply–Demand Modeling – German Gas & LNG Market ⚡

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

**Author:** Mohit Kumar  
**Email:** mohitkr.h@gmail.com  

---

## Project Overview

This project develops a **highly accurate monthly supply–demand model** for Germany's natural gas market, achieving **ensemble R² = 0.761** through systematic feature selection and advanced interpretability techniques.  
The model integrates multiple open data sources into a unified analytical framework that captures the fundamental dynamics of Germany’s gas balance with strong business alignment.

**Key Breakthroughs:**
- **Ensemble R² = 0.761** — Major improvement over baseline models  
- **SHAP-Interpretable** — Clear driver identification and impact quantification  
- **Forecast-Driven Architecture** — Leverages weather and price forecasts  
- **Production-Ready** — Robust scenario testing and validated outputs  

---

## Data Architecture

- **Eurostat:** Gas imports, consumption, production, and Heating Degree Days (HDD)  
- **AGSI:** LNG terminal flows and storage levels  
- **EIA:** US LNG exports, Henry Hub prices  
- **Investing.com:** TTF, JKM, and Brent prices  

**Time Period:** October 2017 – March 2025 (monthly frequency)  
**Final Feature Set:** 7 systematically selected drivers across weather, market, and supply dimensions  

---

## Methodology & Innovations

### Systematic Feature Selection

Developed and tested multiple feature strategies to optimize the balance between **forecastability** and **historical stability**:

| Strategy | Features | R² | Scenario Impact |
|----------|-----------|----|-----------------|
| **Forecast-Heavy** | 7 | **0.676** | **+81 MMcm** |
| Balanced | 7 | 0.613 | +45 MMcm |
| Conservative | 7 | 0.629 | +69 MMcm |

---

### Ensemble Architecture
- **40% LightGBM** with optimized 7-feature configuration  
- **60% Seasonal Naive** baseline for seasonal consistency  
- **Optimal weights** calibrated dynamically for maximum accuracy  

---

### Advanced Interpretability
Comprehensive SHAP analysis revealing deep market behavior:
- **718 MMcm** impact from **Heating Degree Days (HDD)** — the dominant demand driver  
- **445 MMcm** impact from **6-month import patterns** — anticipatory storage management  
- **131 MMcm** from **TTF price changes** — reflects **supply response**, not demand trigger  

---

## Key Results & Achievements

### Model Performance

| Model | R² | Improvement vs Baseline | Business Readiness |
|-------|-----|------------------------|--------------------|
| **Ensemble (Final)** | **0.761** | **+0.977** | ✅ Production Ready |
| LightGBM Only | 0.676 | +0.892 | ✅ |
| Seasonal Naive | -0.216 | Baseline | ⚠️ |

---

### SHAP-Driven Business Insights

#### **Weather Dominance Validated**
- **Heating_Degree_Days:** 718 MMcm impact (0.949 correlation)  
- Confirms Germany’s gas system is overwhelmingly **demand-led**  
- Enables **cold snap preparedness** through weather forecast integration  

#### **Strategic Import Intelligence**
- **Gas_Imports_lag6:** +445 MMcm — winter preparation horizon  
- **Gas_Imports_lag12:** -351 MMcm — annual inventory cycling  
- Reflects **strategic LNG and pipeline import coordination**  

#### **Market Mechanism Understanding**
- **TTF Price Impact:** +131 MMcm — price signals indicate **supply adjustments**, not demand shifts  
- Demonstrates **European market flexibility**: supply adapts to maintain balance  

---

### Scenario Response Capabilities

| Scenario | Impact | Business Interpretation |
|----------|---------|------------------------|
| **Cold Snap (+20% HDD)** | **+81 MMcm** | Immediate supply ramp-up required |
| **Mild Winter (-15% HDD)** | **-105 MMcm** | Reduced supply need; stable system response |
| **Price Shock (+25% TTF)** | +0 MMcm | Confirms price inelasticity |
| **Import Reduction (-15%)** | +0 MMcm | System resilience validated via storage buffers |

---

📄 License

This project is licensed under the MIT License

---

Achievement Highlights

- 76.1% variance explained in Net Supply Position
- 718 MMcm weather impact quantified via SHAP
- +81 MMcm cold snap response verified
- Resilient and production-ready architecture

---

### Usage & Deployment
git clone https://github.com/mohit-kumar-3Q/german-gas-lng-market-model.git
cd german-gas-lng-market-model

