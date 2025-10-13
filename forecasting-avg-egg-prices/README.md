# Forecasting U.S. Egg Prices (April 2025)

### Objective
The goal of this project was to forecast the **average U.S. retail price of a dozen eggs for April 2025** using historical data from the Federal Reserve Economic Data (FRED) database.

Dataset: [APU0000708111](https://fred.stlouisfed.org/series/APU0000708111)


### Data Summary
- **Time Period:** January 1980 – February 2025  
- **Variables:** Observation Date, Average Monthly Price (USD per dozen, not seasonally adjusted)  
- **Source:** FRED, U.S. Bureau of Labor Statistics  

---

### Methodology
Forecasting models used in this project include:

| Model | Description |
|--------|--------------|
| Linear Regression | Captures linear upward trends and seasonality using lag variables |
| Random Forest | Ensemble model to detect nonlinear price behavior |
| Neural Network | Captures complex nonlinear patterns |
| ARIMA | Traditional time-series model focusing on autocorrelation structure |

**Feature Engineering:**
- Created lag variables (`Lag_1`, `Lag_2`) representing one- and two-month lags  
- Split data into:  
  - Training (1980–2019)  
  - Testing Phase 1 (2020–2023)  
  - Testing Phase 2 (2024)  
  - Forecasting (March–April 2025)

---

### Evaluation Metrics
- Root Mean Square Error (RMSE)  
- Mean Absolute Error (MAE)  
- Adjusted R-Squared, AIC, BIC, and CV-RMSE

Linear Regression performed best during volatile periods (2020–2023), while Random Forest performed slightly better during stabilization (2024).

---

### Forecast Results
| Model | Forecasted April 2025 Price | Notes |
|--------|-----------------------------|-------|
| Linear Regression | **$5.83** | Best during volatile periods |
| Random Forest | $4.04 | Smooths variation; slightly underestimates spikes |
| Neural Network | $3.92 | Underfits recent spikes |
| ARIMA | $3.68 | Missed inflation trends |

The **final selected model** was **Linear Regression**, as it captured both seasonal demand (Easter period) and the post-inflation upward trend.

---

### Insights
- Forecast accuracy improves when combining statistical evaluation with **economic context**.  
- Linear Regression, despite not having the lowest RMSE, reflected **real-world market behavior** better.  
- Volatility in egg prices is influenced by **avian flu outbreaks, inflation, and seasonal demand**.

---

### Files in This Repository
| File | Description |
|------|--------------|
| [`APU0000708111.csv`](./APU0000708111.csv) | Raw dataset from FRED |
| [`Forecasting_AvgEggPrices_Rscript.pdf`](./Forecasting_AvgEggPrices_Rscript.pdf) | Full R script and project summary |

---

### Tools & Technologies
**Languages:** R  
**Libraries:** `forecast`, `caret`, `ggplot2`, `randomForest`, `nnet`  
**Techniques:** Time Series Forecasting, Model Evaluation, Feature Engineering  

---

### Key Takeaways
- Linear Regression provided the most interpretable and contextually accurate forecast.  
- Data-driven methods must consider external economic events.  
- Combining predictive modeling and domain knowledge enhances forecast reliability.  

---

*This project was completed as part of ECON 670 — Advanced Economics & Business Forecasting (Spring 2025) at St. Cloud State University.*
