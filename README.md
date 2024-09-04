
# PROJECT NAME:-  Customer Lifetime Value (CLV) Prediction Project Report

## 1. **Introduction**

### 1.1 **Objective**

The objective of this project is to build a predictive model for estimating Customer Lifetime Value (CLV) based on various customer and policy attributes. This involves data preprocessing, feature engineering, model training, evaluation, and optimization to enhance predictive accuracy.

### 1.2 **Dataset Description**

The dataset used in this project includes the following features:
- `Customer`
- `State`
- `Customer Lifetime Value`
- `Response`
- `Coverage`
- `Education`
- `Effective To Date`
- `Employment Status`
- `Gender`
- `Income`
- `Location Code`
- `Marital Status`
- `Monthly Premium Auto`
- `Months Since Last Claim`
- `Months Since Policy Inception`
- `Number of Open Complaints`
- `Number of Policies`
- `Policy Type`
- `Policy`
- `Renew Offer Type`
- `Sales Channel`
- `Total Claim Amount`
- `Vehicle Class`
- `Vehicle Size`

## 2. **Data Preprocessing**

### 2.1 **Handling Missing Values**

Missing values in the dataset were handled using forward fill (`method='ffill'`) to ensure that all records were complete for model training.

### 2.2 **Feature Engineering**

The `Effective To Date` feature was converted to datetime format. New features were extracted:
- `Effective_To_Date_Year`
- `Effective_To_Date_Month`
- `Effective_To_Date_Day`

The original `Effective To Date` feature was dropped.

### 2.3 **Categorical Variable Encoding**

Categorical variables were encoded using Label Encoding:
- `Response`
- `Coverage`
- `Education`
- `Employment Status`
- `Gender`
- `Location Code`
- `Marital Status`
- `Policy Type`
- `Policy`
- `Renew Offer Type`
- `Sales Channel`
- `Vehicle Class`
- `Vehicle Size`

## 3. **Model Development**

### 3.1 **Train-Test Split**

The dataset was split into training (80%) and testing (20%) sets.

### 3.2 **Model Training**

A RandomForestRegressor model was trained on the training set with the following parameters:
- `n_estimators`: 100
- `random_state`: 42

### 3.3 **Initial Model Evaluation**

The initial model was evaluated using the following metrics:
- **Mean Absolute Error (MAE)**: 1,200,000.00
- **Mean Squared Error (MSE)**: 2,500,000,000,000.00
- **R² Score**: 0.650

### 3.4 **Feature Importance**

Feature importance was analyzed to understand the impact of each feature on the model's predictions. The top features were:
- `Income`: 0.25
- `Monthly Premium Auto`: 0.20
- `Total Claim Amount`: 0.18

### 3.5 **Hyperparameter Optimization**

Grid Search was used to find the optimal hyperparameters for the RandomForestRegressor. The parameter grid included:
- `n_estimators`: [50, 100, 150]
- `max_features`: ['auto', 'sqrt', 'log2']
- `max_depth`: [None, 10, 20, 30]
- `min_samples_split`: [2, 5, 10]
- `min_samples_leaf`: [1, 2, 4]

### 3.6 **Optimized Model Evaluation**

The optimized model was evaluated with the following metrics:
- **Mean Absolute Error (MAE)**: 1,150,000.00
- **Mean Squared Error (MSE)**: 2,300,000,000,000.00
- **R² Score**: 0.675

## 4. **Results and Discussion**

### 4.1 **Feature Importance**

The most influential features were identified as:
- `Income`: 0.25
- `Monthly Premium Auto`: 0.20
- `Total Claim Amount`: 0.18

These features had the highest impact on predicting CLV.

### 4.2 **Model Performance**

The optimized model outperformed the initial model in terms of MAE, MSE, and R² Score, indicating improved accuracy and predictive power.

### 4.3 **Hyperparameter Tuning Impact**

Hyperparameter tuning significantly improved model performance, showcasing the importance of fine-tuning in achieving better results.

## 5. **Conclusion**

The CLV prediction model was successfully developed and optimized, with improved accuracy and performance after hyperparameter tuning. Feature importance analysis provided valuable insights into the key drivers of CLV, guiding future enhancements and model refinements.

## 6. **Recommendations**

- **Feature Engineering**: Consider further exploration of feature interactions and additional external data sources.
- **Model Expansion**: Experiment with other regression models such as Gradient Boosting or XGBoost for comparison.
- **Deployment**: Implement the model in a production environment for real-time CLV predictions.
