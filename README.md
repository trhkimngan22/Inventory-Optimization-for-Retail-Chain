# Inventory Optimization for Retail Chain

## Overview
This project analyzes historical sales data for a multi‑store retail chain and builds a time‑series forecast to support inventory optimization decisions. The notebook covers data cleaning, exploratory analysis, seasonality diagnostics, and SARIMA, XGBoost forecasting.

## Project Structure
- data/demand-forecasting-kernels-only/
	- train.csv # using for this project
	- test.csv
- src/
	- notebook.ipynb
	- requirements.txt

## Dataset
Data fields:
- date: Date of sale
- store: Store ID
- item: Item ID
- sales: Units sold

## Environment
- Python 3.9+

## Setup
1) Create and activate a virtual environment.
2) Install dependencies:
	
`pip install -r src/requirements.txt`

## How to Run
1) Open [src/notebook.ipynb](src/notebook.ipynb) in Jupyter/VS Code.
2) Run all cells from top to bottom.

## Outputs
- EDA charts: sales trends, seasonality, store/item comparisons.
- SARIMA model evaluation metrics and forecast plots.
- XGBoost model for predicting daily sales trends.

## Model Performance Summary
Model performance was evaluated using standard forecasting metrics: MAE, RMSE, and MAPE.

### SARIMA: Strategic Monthly Forecasting
- Training set: MAE = 165,868.68 | RMSE = 329,294.72 | MAPE = 24.90%
- Validation set: MAE = 11,317.88 | RMSE = 12,449.56 | MAPE = 1.31%

SARIMA performs best for high-level monthly demand planning. The validation MAPE of 1.31% indicates that the model captures overall trend and seasonality well, making it useful for procurement, warehouse capacity planning, and medium-term inventory decisions.

### XGBoost: Operational Daily Forecasting
- Test set: MAPE = 15.79%

XGBoost is used for more granular daily item-store level forecasting. Although its MAPE is higher than SARIMA, the task is more complex because daily SKU-level demand contains more noise, local fluctuations, and short-term variation. The result is still useful for day-to-day shelf-stocking and local store allocation decisions.

### Key Takeaways
- The dual-model approach supports both macro-level and micro-level inventory decisions.
- SARIMA provides a reliable monthly forecast for strategic planning.
- XGBoost provides actionable daily forecasts for operational inventory optimization.
- Lag features, rolling windows, and log transformation help XGBoost handle high-variance daily sales data.
