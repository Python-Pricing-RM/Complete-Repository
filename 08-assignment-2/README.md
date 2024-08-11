# Predictive Analytics with scikit-learn and sktime

## Objective
This assignment aims to provide students with hands-on experience in predictive analytics using Python, scikit-learn, and sktime. The focus is on applying pipelining predictions, unsupervised learning, PCA, and time series analysis to the hotel-bookings dataset, specifically focusing on cancellations.

## Tasks

### Task 1: Data Preparation
1. Load the dataset and display the first few rows.
2. Handle missing values appropriately.
3. Convert relevant columns to the correct data types (e.g., dates).
4. Create new columns if needed (e.g., total stay duration).

### Task 2: Unsupervised Learning with PCA and Clustering
1. **Objective**: Segment customers and reduce dimensionality for better visualization, focusing on bookings that were canceled.
2. **Steps**:
    - Select relevant features for clustering (e.g., `lead_time`, `adr`, `stays_in_weekend_nights`, `stays_in_week_nights`, `total_of_special_requests`).
    - Standardize the selected features.
    - Apply PCA to reduce dimensionality and inspect the loadings to distinguish between `City Hotel` and `Resort Hotel`.
    - Apply K-Means clustering to segment customers and plot the clusters on the PCA coordinates.
    - Evaluate the clustering using the silhouette score. You can use `silhouette_score` from `sklearn.metrics`.

### Task 3: Supervised Learning with Pipelining Predictions
1. **Objective**: Predict whether a booking will be canceled or not.
2. **Steps**:
    - Define the target variable (`is_canceled`) and features.
    - Split the dataset into training and test sets.
    - Create a preprocessing pipeline using `ColumnTransformer` to handle numerical and categorical features, including PCA components.
    - Use a `Pipeline` to streamline preprocessing and model training.
    - Train a classification model (e.g., `LogisticRegression`, `RandomForestClassifier`) and evaluate its performance.

### Task 4: Time Series Analysis
1. **Objective**: Forecast the average daily rate (ADR) over time.
2. **Steps**:
    - Convert the `reservation_status_date` to a datetime object and set it as the index.
    - Resample the data to a monthly frequency, calculating the mean ADR for each month.
    - Split the time series data into training and test sets.
    - Create a pipeline using `sktime` for time series forecasting.
    - Train a time series forecasting model (e.g., `ARIMA`, `ExponentialSmoothing`) and evaluate its performance.

## Additional Tips
- Use `df.head()` and `df.describe()` to understand the dataset.
- Use `SimpleImputer` for handling missing values and `StandardScaler` for standardization.
- Experiment with different models and hyperparameters to improve performance.
- Use `train_test_split` from `sklearn.model_selection` to split the data.
- Visualize the results using Matplotlib and Seaborn.
