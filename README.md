# Inventory Optimization for Retail Chain

## Overview
This project analyzes historical sales data for a multi‑store retail chain and builds a time‑series forecast to support inventory optimization decisions. The notebook covers data cleaning, exploratory analysis, seasonality diagnostics, and SARIMA forecasting.

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

## Notes
- The model is trained on monthly aggregated sales. For store/item‑level forecasting, extend the notebook to model each series separately.