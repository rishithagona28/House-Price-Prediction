# 🏡 House Price Prediction: California Housing

> An end-to-end regression workflow that estimates median house values from census-block data: exploratory analysis, feature engineering, outlier handling, and a Linear Regression model.

![Python](https://img.shields.io/badge/Python-3.x-3776AB?logo=python&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikitlearn&logoColor=white)
![Google Colab](https://img.shields.io/badge/Google%20Colab-F9AB00?logo=googlecolab&logoColor=white)

---

## 📌 Overview

This project predicts the **median house value** of California districts using the classic
**California Housing** dataset (1990 census). It was built in Google Colab and exported to a single
script, [`house.py`](house.py), that walks through the full machine-learning workflow step by step.

## ✨ What the project covers

| Step | What happens |
|---|---|
| **1. Data loading** | Upload `housing.csv` in Colab, and also load the dataset via `sklearn.datasets.fetch_california_housing` |
| **2. Missing values** | Median imputation for `total_bedrooms` (`SimpleImputer`) |
| **3. Feature engineering** | New ratio features: **RoomsPerHousehold**, **BedroomsPerRoom**, **PopulationPerHousehold** |
| **4. Binning** | Each engineered feature bucketed into 5 levels (*Low → High*) with `pd.cut` and visualised |
| **5. Outlier analysis** | Compares 4 strategies: Z-score removal, IQR removal, winsorizing (capping), and log transform |
| **6. Scaling & encoding** | `StandardScaler` on numeric features, `LabelEncoder` for buckets, One-Hot encoding for `ocean_proximity` |
| **7. EDA** | Correlation heatmaps, scatter matrix, target distribution, income box plot |
| **8. Modelling** | **Linear Regression** trained on an 80/20 train–test split |
| **9. Evaluation** | MAE, MSE, RMSE and R², plus an *actual vs. predicted* scatter plot |

## 🗂️ Project structure

```
House-Price-Prediction/
├── house.py      # Full pipeline (exported from Google Colab)
└── README.md
```

## 🚀 How to run

The script was written for **Google Colab**, which is the easiest way to run it:

1. Download `housing.csv` (the [California Housing Prices dataset on Kaggle](https://www.kaggle.com/datasets/camnugent/california-housing-prices)).
2. Open [Google Colab](https://colab.research.google.com/), create a notebook and paste in the contents of `house.py`
   (or upload the file and run it with `%run house.py`).
3. Run it. When prompted, upload `housing.csv`.

The metrics (MAE, RMSE, R²) and all charts are printed as the script runs.

To run it locally instead, install the dependencies and remove the `google.colab` upload lines:

```bash
pip install numpy pandas matplotlib seaborn scikit-learn scipy
```

## 🧰 Tech stack

**Python** · **pandas** · **NumPy** · **scikit-learn** · **SciPy** · **Matplotlib** · **Seaborn** · **Google Colab**

## 📝 Notes & next steps

- The *single-house prediction* section near the end expects a saved model, scaler and encoder
  (the `pickle.load` lines are commented out). Saving these after training would make it fully runnable.
- `DecisionTreeRegressor` and `RandomForestRegressor` are imported. Comparing them against
  Linear Regression is a natural next experiment, since tree models usually do much better on this dataset.

> 🔗 **Follow-up project:** [GharAI](https://github.com/rishithagona28/Ghar-Ai--The-house-price-prediction-website) takes these ideas further, with real **Indian** listings, gradient boosting, explainable predictions and a full Zillow-style web app.

## 👩‍💻 Author

**Rishitha Naga Durga Gona**: [@rishithagona28](https://github.com/rishithagona28)
