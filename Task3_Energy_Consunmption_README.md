# Task 3: Energy Consumption Forecasting

**DevelopersHub Corporation — Data Science & Analytics Internship (Advanced Task Set)**

## Objective
Forecast household energy consumption using three different forecasting approaches — **ARIMA**, **Prophet**, and **XGBoost** — and compare their performance.

## Dataset
[UCI Individual Household Electric Power Consumption](https://archive.ics.uci.edu/dataset/235/individual+household+electric+power+consumption)
- ~2.07 million minute-level readings, Dec 2006 – Nov 2010, single household in Sceaux, France.
- 9 columns: Date, Time, Global_active_power, Global_reactive_power, Voltage, Global_intensity, Sub_metering_1/2/3.

## Approach
1. **Data cleaning** — parsed semicolon-separated file, handled `?` as missing (~1.25% of rows), combined Date+Time into a datetime index, time-based interpolation for gaps.
2. **Resampling** — aggregated minute-level data to **daily average Global Active Power (kW)**, the standard framing for this dataset in forecasting tasks.
3. **EDA** — examined monthly/yearly seasonality (winter demand peaks) and day-of-week patterns.
4. **Train/test split** — last 90 days held out as test set.
5. **Models:**
   - **ARIMA(5,1,2)** (statsmodels) — classical statistical baseline, stationarity checked via ADF test.
   - **Prophet** — automatic yearly + weekly seasonality decomposition.
   - **XGBoost** — supervised reframing with lag features (1/2/3/7/14 days), rolling mean/std, and calendar features.
6. **Evaluation** — MAE, RMSE, R² on the 90-day test window.

## Results

| Model    | MAE    | RMSE   | R²      |
|----------|--------|--------|---------|
| XGBoost  | 0.2034 | 0.2918 | -0.1067 |
| Prophet  | 0.2159 | 0.2987 | -0.1595 |
| ARIMA    | 0.2907 | 0.3709 | -0.7881 |

**XGBoost performed best**, benefiting from lag/rolling features that capture short-term autocorrelation. Prophet was a close second thanks to automatic seasonality handling. ARIMA struggled most, since a simple (p,d,q) order doesn't capture the yearly seasonal pattern well (a SARIMA extension would likely help).

## Files
- `Task3_Energy_Forecasting.ipynb` — notebook source
- `Task3_Energy_Forecasting_executed.ipynb` — fully executed notebook with all outputs
- `outputs/` — exported charts (daily series, EDA, forecasts, model comparison, feature importance)
- `data/household_power_consumption.txt` — raw dataset

## How to Run
```bash
conda activate dataeng
pip install statsmodels xgboost prophet
jupyter nbconvert --to notebook --execute Task3_Energy_Forecasting.ipynb
```

## Next Steps
- Hyperparameter tuning (auto_arima for ARIMA orders, grid/random search for XGBoost).
- SARIMA to explicitly model yearly seasonality.
- Add exogenous regressors (e.g. weather/temperature data).
- Forecast at hourly resolution for shorter-horizon use cases.
