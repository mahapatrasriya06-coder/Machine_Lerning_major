# King County House Price Analysis & Prediction Dashboard

An interactive Streamlit dashboard that analyzes and predicts house prices using two King County housing datasets. The project covers data cleaning, exploratory data analysis, outlier detection, geographic visualization, and regression-based price prediction.

## Overview

This project loads and compares two related housing datasets (`kc_house_data.csv` and `king_country_dataset.csv`), cleans and engineers features from them, visualizes key patterns, trains a Linear Regression model on each dataset, and lets users interactively predict house prices based on input features — all within a single Streamlit app.

## Features

- **Data Cleaning:** Handles missing values (median imputation), removes duplicates, and filters out invalid ($0) prices
- **Feature Engineering:** Calculates `price_per_sqft` and `house_age` for both datasets
- **Exploratory Data Analysis:** Summary statistics, histograms, boxplots, and correlation heatmaps using Plotly
- **Outlier Detection:** IQR-based outlier filtering across numeric features
- **Geographic Visualization:** Scatter map of house prices by latitude/longitude
- **Key Insights:** Top correlated price factors and most expensive zip codes/cities
- **Regression Modeling:** Linear Regression models trained separately on both datasets, evaluated with R², MAE, and RMSE
- **Interactive Prediction:** Users input square footage, bedrooms, and bathrooms to get real-time price estimates from both models

## Tech Stack

- **Language:** Python
- **Data Handling:** Pandas, NumPy
- **Modeling:** Scikit-Learn (Linear Regression; Random Forest and Gradient Boosting imported for future use)
- **Visualization:** Plotly Express, Plotly Graph Objects, Matplotlib, Seaborn
- **Deployment:** Streamlit

## Project Structure

```
ML/
├── Major_Project/
│   ├── house_price.py              # Main Streamlit app (this script)
│   ├── kc_house_data.csv           # Dataset 1
│   └── king_country_dataset.csv    # Dataset 2
├── requirements.txt
└── README.md
```

*(Update this structure if your folder names or paths differ.)*

## Setup & Installation

### 1. Clone the repository

```bash
git clone https://github.com/your-username/house-price-prediction-dashboard.git
cd house-price-prediction-dashboard
```

### 2. Create and activate a virtual environment

```bash
python -m venv .venv
source .venv/bin/activate      # On Windows: .venv\Scripts\activate
```

### 3. Install dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn streamlit plotly
```

Or, if you have a `requirements.txt`:

```bash
pip install -r requirements.txt
```

### 4. Add the datasets

Make sure `kc_house_data.csv` and `king_country_dataset.csv` are placed inside the `Major_Project/` folder, matching the paths used in the script.

## Running the Project

1. **Navigate to your project folder:**

   ```bash
   cd /Users/sriyamahapatra/Documents/ML
   ```

2. **Activate your virtual environment:**

   ```bash
   source .venv/bin/activate
   ```

3. **Run the Streamlit dashboard:**

   ```bash
   streamlit run Major_Project/house_price.py
   ```

4. Streamlit will open the app in your browser automatically. If not, open the local URL shown in the terminal (usually `http://localhost:8501`).

## How It Works

1. **Load & Clean:** Both datasets are loaded, checked for missing values, and cleaned (median imputation, duplicate removal, invalid price filtering).
2. **Feature Engineering:** `price_per_sqft` and `house_age` are calculated for both datasets.
3. **Visualization:** Histograms, boxplots, and correlation heatmaps are generated for each dataset using Plotly, alongside a geographic scatter plot of prices by location.
4. **Insights:** The app prints and displays the top correlated price factors and the most expensive zip codes/cities.
5. **Modeling:** A Linear Regression model is trained independently on each dataset using `sqft_living`, `bedrooms`, and `bathrooms` as features, and evaluated using R², MAE, and RMSE.
6. **Prediction:** Users enter property details in the sidebar/form, and the app returns price estimates from both models along with their average.

## Model Features Used

- `sqft_living`
- `bedrooms`
- `bathrooms`

## Future Improvements

- Train and compare Random Forest / Gradient Boosting models (already imported) against Linear Regression
- Add more features to the model (location, house age, price per sqft) to improve accuracy
- Add cross-validation for more robust performance metrics
- Fix indentation in the geographic scatter plot section for cleaner logic
- Deploy publicly via Streamlit Community Cloud

## Author

**Sriya Mahapatra**
