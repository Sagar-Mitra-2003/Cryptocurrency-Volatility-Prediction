# 🚀 Cryptocurrency Volatility Prediction  
*A complete Machine Learning pipeline for forecasting cryptocurrency volatility using historical OHLC, volume, and market capitalization data.*

![Volatility](https://img.shields.io/badge/ML-Regression-blue) ![Python](https://img.shields.io/badge/Python-3.9%2B-green) ![Framework](https://img.shields.io/badge/Framework-ScikitLearn-orange)

---

## 📘 Project Overview
Cryptocurrency markets are extremely volatile.  
This project builds a **predictive model** that forecasts **next-day volatility** (using the intraday range `(High-Low)/Open` as a proxy).  

It follows a full **data science workflow**:
1. Data collection (historical OHLC, volume, market cap)
2. Preprocessing & cleaning  
3. Feature engineering (returns, moving averages, rolling volatility, liquidity ratios)
4. Exploratory Data Analysis (EDA)  
5. Model training (Random Forest & Gradient Boosting)  
6. Evaluation using RMSE, MAE, and R²  
7. Deployment with Streamlit (optional demo app)

---

## 🧾 Dataset
- Historical daily data for 50+ cryptocurrencies.  
- Columns: `date`, `symbol`, `open`, `high`, `low`, `close`, `volume`, `market_cap`.  
- Downloadable from: [Google Drive Link](https://drive.google.com/file/d/1iVhJKnfAR-Vm4JHC-TY4-kXEcfH5C_ky/view?usp=drive_link)

---

## 🧩 Features Engineered
| Feature | Description |
|----------|--------------|
| `return` | Daily return = (Close − Open) / Open |
| `intraday_range` | Volatility proxy = (High − Low) / Open |
| `ma_7`, `ma_30` | 7-day & 30-day moving averages |
| `vol_7`, `vol_30` | Rolling standard deviation of returns |
| `liquidity` | Volume / Market Cap |
| `next_day_vol` | Target — next day’s intraday range |

---

## 📊 Model Training
Two models were trained and compared:
- **RandomForestRegressor**
- **GradientBoostingRegressor**

Evaluation Metrics:
| Model | RMSE | MAE | R² |
|--------|------|------|----|
| RandomForest | varies |  |  |
| GradientBoosting |  |  |  |

Best model: **Random Forest (based on RMSE)**  

*(Exact numbers appear in `evaluation_metrics.csv`)*

---

## 📈 Visualizations
- Target distribution (`eda_nextdayvol_dist.png`)  
- Correlation heatmap (`eda_correlation.png`)  
- Time-series plots (`ts_Bitcoin.png`, etc.)

---

## 💾 Outputs
All results are saved in the `ml_submission_outputs/` folder:
- `cleaned_dataset.csv`
- `features_dataset.csv`
- `best_model.pkl`
- `evaluation_metrics.csv`
- `eda_nextdayvol_dist.png`
- `ts_<symbol>.png`
- `README.md`
- `requirements.txt`
- `app.py` (Streamlit interface)

---

## 🧠 Run Locally
```bash
pip install -r ml_submission_outputs/requirements.txt
jupyter notebook Crypto_Volatility_Prediction_Project.ipynb
```

---

## 🌐 Streamlit App (Optional)
To test predictions interactively:
```bash
streamlit run ml_submission_outputs/app.py
```

This will launch a simple web interface where you can upload new data and get predicted next-day volatility.

---

## 🧰 Tools & Libraries
- **Python** 3.9+
- **Pandas**, **NumPy**, **Matplotlib**, **Seaborn**
- **Scikit-Learn**
- **Streamlit**
- **gdown** (for Drive download)

---

## 🏗 Folder Structure
```
crypto-volatility-prediction/
│
├── Crypto_Volatility_Prediction_Project.ipynb
├── ml_submission_outputs/
│   ├── cleaned_dataset.csv
│   ├── features_dataset.csv
│   ├── best_model.pkl
│   ├── evaluation_metrics.csv
│   ├── eda_nextdayvol_dist.png
│   ├── ts_Bitcoin.png
│   ├── README.md
│   ├── requirements.txt
│   └── app.py
└── README.md
```

---

## 🧑‍💻 Author
**Sagar Mitra**  
Machine Learning & Data Analysis Enthusiast  
📧 your_email@example.com  
🌐 [GitHub Profile](https://github.com/yourusername)
