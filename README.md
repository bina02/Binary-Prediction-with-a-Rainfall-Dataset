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
python 3.X
## 2.2 Libraries
- pandas
- numpy
- scikit-learn
- matplotlib
- seaborn   
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

# 4. Model Architecture & Methodlogy
## 4.1 Models
- Logistic Regression (C=1)
## 4.2 Key Techniques
- KFOLD cross validation
# 5. Results & Evaluation
## 5.1 Metrics
ROC AUC score
## 5.2 Performance
### 5.2.1 First update
<img width="567" height="454" alt="image" src="https://github.com/user-attachments/assets/5d6714a5-a936-4c15-a103-a61ed24beac2" />

**ROC AUC score: 0.8777(logistic regression)**
# 6. Future Improvements
- Experiment with various classifiers such as XGBoost, LightGBM, and CatBoost.
- Perform hyperparameter tuning using GridSearch.
