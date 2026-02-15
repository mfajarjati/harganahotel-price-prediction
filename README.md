# 🏨 Hargana Hotel – AI Dynamic Pricing System

An end-to-end Machine Learning pipeline for hotel dynamic pricing simulation using historical booking data, hotel metadata, weather variables, and AI regression models.

This project builds, evaluates, and deploys models to simulate adaptive hotel pricing strategies.

---

# 📌 Project Overview

This notebook implements:

- Data Cleaning & Preprocessing
- Feature Engineering
- Exploratory Correlation Analysis
- Multi-Model Regression Comparison
- Feature Importance Analysis
- Dynamic Pricing Simulation
- Multi-Hotel Comparison
- Model Export for Web Integration

Target variable:

```
price
```

---

# 📂 Dataset Structure

The system uses multiple datasets:

| Dataset | Description |
|----------|------------|
| `hotels_data.csv` | Hotel metadata (rating, category, amenities, coordinates) |
| `hotels_price.csv` | Historical booking prices |
| `hotels_reviews.csv` | Review data (optional) |
| `nearby_places.csv` | Nearby attraction features (optional) |
| `weather.csv` | Weather conditions per date |

---

# ⚙️ Data Processing Pipeline

## 1️⃣ Price Cleaning

Converts strings like:

```
Rp336.648 → 336648.0
```

Creates:

```
Price_numeric
```

---

## 2️⃣ Feature Engineering

Generated features include:

- `rating`
- `reviews_count`
- `amenities_count`
- `hotel_star`
- `near_center_score`
- `booking_month`
- `booking_quarter`
- `is_holiday_weekend`
- `weather_encoded`

Distance to city center calculated using Haversine formula.

---

## 3️⃣ Train / Validation / Test Split

```
Train: 80%
Validation: 10%
Test: 10%
```

Features normalized using:

```
StandardScaler
```

---

# 🤖 Models Implemented

| Model | Description |
|--------|------------|
| Linear Regression | Baseline model |
| SVR (RBF) | Non-linear regression |
| Random Forest | Ensemble tree model |
| XGBoost | Gradient boosting (best performer) |
| ARIMA | Time series model |
| SARIMAX | Time series + exogenous variables |

Evaluation Metrics:

- R²
- RMSE
- MAE

---

# 🏆 Best Model

The best performing model:

```
XGBoost Regressor
```

Used for:

- Feature importance
- Prediction visualization
- Dynamic pricing simulation
- Multi-hotel comparison

---

# 📊 Feature Importance

Top influencing variables typically include:

- Rating
- Hotel star category
- Reviews count
- Amenities count
- Location proximity
- Holiday/weekend indicator

Visualization:

```
Barplot of top 10 important features
```

---

# 📈 Prediction Evaluation

Visualizations include:

- Scatter plot (Actual vs Predicted)
- Error distribution histogram
- Mean comparison (Actual vs Predicted)

---

# 🔄 Dynamic Pricing Simulation

## Core Function

```
dynamic_pricing()
```

Simulates future hotel prices using:

- Historical price baseline
- XGBoost AI prediction
- Weekend adjustment
- Holiday adjustment
- Random demand fluctuation

---

# 🏨 Multi-Hotel Comparison

Function:

```
compare_hotels_pricing()
```

Allows comparison across multiple hotel IDs for:

- Dynamic price evolution
- Competitive positioning
- AI-driven price gap analysis

Outputs:

- Table comparison
- Line chart visualization

---

# 💾 Model Export

Exports:

```
xgboost_hotel_model.pkl
xgboost_hotel_model.json
scaler_hotel.pkl
```

Ready for:

- Flask backend
- FastAPI service
- Node.js API integration
- Web-based decision support system

---

# 🧠 System Architecture

```
Raw Data
   ↓
Cleaning
   ↓
Feature Engineering
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Dynamic Simulation
   ↓
Export Model
   ↓
Web Deployment
```

---

# 📌 Requirements

```
pandas
numpy
scikit-learn
xgboost
lightgbm
catboost
statsmodels
matplotlib
seaborn
joblib
tabulate
```

Install:

```bash
pip install pandas numpy scikit-learn xgboost lightgbm catboost statsmodels matplotlib seaborn joblib tabulate
```

---

# ⚠️ Notes

- Ensure consistent feature order when predicting.
- Scaler must match the trained model.
- Model output depends heavily on price distribution in dataset.
- Historical data gaps are filled using nearest-date strategy.

---

# 🎯 Use Case

This system can be integrated into:

- Hotel revenue management systems
- AI-based pricing recommendation platforms
- Travel tech dashboards
- Decision support systems
- Academic research on dynamic pricing

---

# 📚 Research Context

This project aligns with:

- Machine Learning for Revenue Management
- AI-based Dynamic Pricing
- Hybrid Exogenous + Time Series Modeling
- Smart Tourism Analytics

---

# 👨‍💻 Author

Developed for:

**AI-Powered Dynamic Hotel Pricing Decision Support System**

---

# 📜 License

For research and educational use only.
Commercial usage requires adaptation and compliance review.
