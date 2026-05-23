# Retail Sales Data Transformation Project

## Overview

This project demonstrates a retail sales data transformation workflow using a raw dataset with quality issues. The goal is to clean, validate, and enrich the retail store sales data to produce a higher-quality dataset ready for analysis.

## What this project does

- loads the raw dataset from `dirty_retail_store_sales.csv`
- inspects data structure, types, and missing values
- converts transaction dates to proper datetime values
- trims whitespace from categorical text fields
- fills missing pricing, quantity, and total spent values using logical rules
- handles missing item names and discount values
- removes unusable rows with insufficient data
- checks for duplicates and invalid values
- computes derived features such as day of week and weekend indicator
- exports a cleaned version of the dataset as `cleaned_retail_data.csv`

## Files in this repository

- `dirty_retail_store_sales.csv` - raw retail sales dataset with quality issues
- `cleaned_retail_data.csv` - cleaned output dataset after transformation
- `transforming_retaildata.ipynb` - Python notebook containing the data cleaning process
- `README.md` - project overview and usage instructions

## Key data cleaning steps

- convert `Transaction Date` to datetime
- strip leading/trailing whitespace in `Category`
- impute missing `Price Per Unit` values by item mode or category median
- calculate missing `Quantity` or `Total Spent` values where possible
- replace missing item names with placeholder values
- treat missing discounts as `0`
- remove rows missing both `Quantity` and `Total Spent`
- validate duplicates and remove invalid numeric records
- add feature columns such as `Day_of_Week` and `Is_Weekend`

## Libraries used

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`

## How to run

1. Open `transforming_retaildata.ipynb` in Jupyter Notebook or JupyterLab.
2. Run the notebook cells sequentially.
3. Review the cleaned dataset and visualizations.

## Notes

This project is useful as a demonstration of practical data cleaning and feature engineering for retail transaction data. The notebook includes a structural audit, missing-value treatment, and simple analysis for weekend sales patterns.
