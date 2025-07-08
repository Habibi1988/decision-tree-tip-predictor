# 🗽 NYC Taxi Tip Prediction using Decision Tree Regressor

This project uses a subset of the [NYC Taxi & Limousine Commission (TLC) Trip Record Dataset](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) to train and evaluate a regression model that predicts **taxi tip amounts** based on various trip features.

## 🎯 Objectives

- Perform data preprocessing with Scikit-Learn
- Train a Decision Tree Regressor model
- Analyze model performance using MSE and R² score
- Identify the most important features influencing tip amount
- Explore the effect of hyperparameters like `max_depth` on model performance

## 🧪 Dataset

Each row in the dataset represents a yellow taxi trip with 13 variables, including:

- `fare_amount`
- `trip_distance`
- `tolls_amount`
- `tip_amount` *(target variable)*  
...and others

The data was obtained from [TLC Trip Record Data](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page) and hosted on IBM Cloud Object Storage for this lab.

## 🛠️ Technologies Used

- Python
- Pandas & NumPy
- Scikit-learn
- Matplotlib

## 📈 Workflow Summary

1. **Data Loading & Exploration**  
   Load the CSV, inspect column correlation with the target variable.

2. **Preprocessing**  
   - Feature normalization (`l1` norm)
   - Removal of non-informative columns (e.g. `VendorID`, `store_and_fwd_flag`, etc.)

3. **Model Training**  
   - Train a `DecisionTreeRegressor` using Scikit-Learn
   - Evaluate using R² and Mean Squared Error (MSE)

4. **Experiments**
   - Vary `max_depth` (e.g. 4, 8, 12) to observe impact on overfitting/underfitting
   - Identify top correlated features (e.g. `fare_amount`, `trip_distance`, `tolls_amount`)
   - Assess performance after dropping uncorrelated features

## 🔍 Key Insights

- **Top 3 influential features**: `fare_amount`, `trip_distance`, `tolls_amount`
- **Optimal max_depth**: Reducing to `max_depth=4` improved generalization
- **Removing low-correlation features**: Little to no effect on model performance

## 📊 Model Evaluation

- **Metrics**: 
  - `MSE`: Lower is better
  - `R²`: Closer to 1 is better

| max_depth | MSE ↓ | R² ↑ |
|-----------|-------|------|
| 4         | ✅ lower | ✅ higher |
| 8         | Baseline | Baseline |
| 12        | ❌ higher | ❌ possibly negative (overfit) |
