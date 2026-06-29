# Binary-Prediction-with-a-Rainfall-Dataset
A machine learning project to predict the probability of precipitation.

# 1. Project Overview
## 1.1 Objective
Building a model to predict whether it will rain the next day based on historical weather data.
## 1.2 Period
2026-06-26 ~ 2026-06-??
## 1.3 Goal
Practicing data preprocessing and optimizing classification models
# 2. Tech stack
## 2.1 Language
python 3.14.3
## 2.2 Libraries
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn   
- imblearn
- xgboost
- lightgbm
- optuna
## 2.3 Environment
Jupyter Notebook (.ipynb)
# 3. Dataset
## 3.1 Data source
https://www.kaggle.com/competitions/playground-series-s5e3
## 3.2 Features
- id
- day
- pressure
- maxtemp (max temperature)
- temparature
- mintemp (min temperature)
- dewpoint
- humidity
- cloud
- sunshine
- winddirection
- windspeed
- rainfall (target)

## 3.3 Preprocessing
Scaling with standard scaler only

# 4. Model Architecture & Methodology
## 4.1 Models
- Logistic Regression
- SVM
- Lightgbm
- XGboost
- Catboost

## 4.2 Key Techniques
- KFOLD cross validation
- Oversampling
- Hyperparameter optimization
# 5. Results & Evaluation
## 5.1 Metrics
ROC AUC score
## 5.2 Performance
### 5.2.1 1st update
<img width="500" height="400" alt="1st_roc_curve" src="https://github.com/user-attachments/assets/0ecae98b-e246-438d-825a-76c9bfc44207" />

**ROC AUC score: 0.8777(logistic regression)**

### 5.2.2 2nd update
#### Changelog 
1. SMOTE oversampling
2. Additional models: SVM, XGBoost, LightGBM, CatBoost
3. Hyperparameter optimization with Optuna
#### details
Using optuna with 20 trials, I optimized parameters based on ROC AUC score K-fold(FOLDS=5) from cross validation on the oversampled data.
The resulting table is summarized in the table below.
|classifier|validation_ROC_AUC_score|
|---|---|
|Logistic_Regression|	0.894567|
|SVC|	0.893608|
|XGBoost|	0.880159|
|lgbm|	0.880149|
|Catboost|	0.889799|

I evaluated models and their parameters, then selected the top three models: \
logistic regression, SVC, Catboost \
I then created an ensemble model using these three models, and compared its performance on the test dataset
|classifier|test_ROC_AUC_score|best parameters|
|---|---|---|
|Logistic_Regression|0.8925|'C': 0.10585286399625815, 'max_iter': 141|
|SVC score|0.8885|'C': 0.17895479795382974, 'kernel': 'linear', 'gamma': 'scale'|
|Catboost|0.8876|'n_estimators': 120, 'max_depth': 8, 'learning_rate': 0.05018726789304549|
|ensemble model|0.8919|-|

The best-performing model was Logistic Regression. Compared to the previous version, the test score improved from 0.8777 to 0.8925.
# 6. Future Improvements
- Experiment with various classifiers such as XGBoost, LightGBM, and CatBoost. (O)
- Perform hyperparameter tuning using GridSearch. (O)
- Oversampling (O)
- Feature engineering
