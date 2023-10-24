# 🏠🏠 Sales Prediction from Media Spend 🔮🔮
![Python version](https://img.shields.io/badge/Python%20version-3.10%2B-lightgrey)
![GitHub last commit](https://img.shields.io/github/last-commit/Taweilo/house_price_prediction)
![GitHub repo size](https://img.shields.io/github/repo-size/Taweilo/house_price_prediction)
![Type of ML](https://img.shields.io/badge/Type%20of%20ML-Regression%20-red)
![License](https://img.shields.io/badge/License-MIT-green)

Badge [source](https://shields.io/)

 <img src="https://www.bouzaien.com/post/house-pricing-prediction/featured.png" width="1100" height="450">
This project will follow the Business Analysis (BA) workflow to address diabetes diagnosis using data mining techniques. The business problem at hand is to create a machine-learning model that can accurately predict the house prices based on the provided features. This model can be utilized by real estate agents to evaluate the property value.

```
├── Image
│   ├── 2.1 Dataset.jpg                           <- dataset image used in the README
│   ├── 2.2 Statistics.jpg                        <- data statistics summary used in the README
│   ├── 2.3 Outcome distribution.jpg              <- outcome distribution image used in the README
│   ├── 2.4 Pairplot.jpg                          <- pairplot image used in the README
│   ├── 5.1 Evaluation.jpg                        <- model summary table used in the README
│   ├── 5.2 RF Confusion matrix.jpg               <- RF Confusion matrix used in the README
│   ├── 5.3 Feature importance.jpg                <- RF feature importance used in the README                          
│
├── Code_Diabetes_Prediction.ipynb                <- code
├── Data_diabetes.csv                             <- dataset
├── LICENSE                                       <- MIT license
├── README.md                                     <- read me
```

## 1. Business Understanding
The goal of this project is to develop a predictive model for diabetes based on various medical attributes of patients. The dataset contains information about patients, including their number of pregnancies, glucose level, blood pressure, skin thickness, insulin level, body mass index (BMI), diabetes pedigree function, age, and the final outcome indicating whether the patient has diabetes (1 for Yes and 0 for No).

## 2. Data Understanding 
The Diabetes dataset was loaded via Colab. The dataset is from Kaggle: https://www.kaggle.com/datasets/akshaydattatraykhare/diabetes-dataset (also please see Data_diabetes.csv attached). Basic data analysis was performed to identify the shape of data, get column names, find missing values, and generate descriptive statistics. The pair plot demonstrated the relationship between variables. The distribution of the target class variable was shown.

* Original Dataset
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/2.1%20Dataset.jpg" width="1000">

* Data Dictionary
 
| Name | Modeling Role | Measurement Level| Description |
| ---- | ------------- | ---------------- | ---------- |
| **Pregnancies** | input | int64 | To express the Number of pregnancies of the patient |
| **Glucose** | input | int64 | To express the Glucose level in the blood of the patient|
| **BloodPressure** | input | int64 | To express the Blood pressure measurement of the patient |
| **SkinThickness** | input | int64 | To express the thickness of the skin of the patient |
| **Insulin** | input | int64 | To express the Insulin level in the blood of the patient |
| **BMI** | input | float64 | To express the Body mass index of the patient |
| **DiabetesPedigreeFunction** | input | float64  | To express the Diabetes percentage of the patient |
| **Age** | input | int64 | To express the age of the patient |
| **Outcome** | target | binary | To express the final result 1 is Yes and 0 is No Diabetes of the patient |

* Statistics
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/2.2%20Statistics.jpg" width="1000">
 
* Pairplot
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/2.4%20Pairplot.png" width="1000">

* Outcome Distribution
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/2.3%20Outcome%20distribution.jpg" width="1000">
 
| Outcome | Count | Note         |
| ------- | ----- | ------------ |
| **0**   | 500   | No Diabetes  |
| **1**   | 268   | Diabetes     |
 
## 3. Data Preparation 
1. Define variables (X and y) 
2. Split the data into train and test datasets; 40% of test data <br>
   train: 460 data<br>
   test:  308 data<br>
  
## 4. Modeling   
Several machine learning models were included. Among all, KNN, Regression Tree, and Random Forest proceeded hyperparameter tuning for better performance:
* Logistic regression
* Gaussian model
* SVM
* KNN
* Regression Tree
* Random Forest with Tuning
  
## 5. Evaluation
<img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/5.1%20Evaluation.jpg" width="500" >
 
* Random Forest has the best performance. The best hyperparameter is: 
 
``` {'n_estimators': 200,
 'min_samples_split': 10,
 'min_samples_leaf': 4,
 'max_features': 'log2',
 'max_depth': 5,
 'bootstrap': True}
```
* Out-of-sample Accuracy of Random Forest:  0.76; Out-of-sample AUC:  0.83; True Positive Rate: 54.1% and False Positive Rate 11.7%.
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/5.2%20RF%20Confusion%20Matrix.jpg" width="500" >
 
* Feature importance can be shown: Glucose in the blood is the most important feature. 
 <img src="https://github.com/Taweilo/Diabetes_Prediction/blob/main/Image/5.3%20Feature%20importance.jpg" width="500" >
 
