# Predict Diabetes Mellitus
* Predicted whether a patient admited to ICU(Intensive Care Unit) has diabetes mellitus or not to help hospitals administer appropriate medical treatment
* Cleaned the data, removed or imputed missing values, analysed relationships between variables and target variables
* Engineered features 
* Performed SMOTE to balance the class distribution 
* Applied 3 models - Logistic Regresion, XGBoost and Random Forest
* Optimised Xgboost and Random Forest models using GridSearchCV 

_This analysis was done for WIDS (Women in Data Science) kaggle competition and represents the collaborative effort of the team I was part of._

# Code and Resources 
- **Python Version:** 3.7
- **Packages:** pandas, numpy, sklearn, matplotlib, seaborn, shap
- **RandomizedSearch:** https://towardsdatascience.com/hyperparameter-tuning-the-random-forest-in-python-using-scikit-learn-28d2aa77dd74 
- **Feature Engineering:** https://www.kaggle.com/jayjay75/3rd-place-nn-wids2020?scriptVersionId=29209297
- **SMOTE**: https://towardsdatascience.com/how-to-effortlessly-handle-class-imbalance-with-python-and-smote-9b715ca8e5a7

# Data Cleaning 
* The data for this problem is provided by MIT’s GOSSIS (Global Open Source Severity of Illness Score)initiative. It contains: 180 features and the target variable 'diabetes mellitus'. 
* Link to dataset: https://www.kaggle.com/c/widsdatathon2021/data



Data Cleaning approach:
* We have an imbalanced dataset, diabetes mellitus accounts only 21,6% of the datapoints from the dataset.
<img width="424" alt="image" src="https://user-images.githubusercontent.com/79809854/117856273-51564400-b283-11eb-898c-a75da46122bc.png">

* visualised missing data and removed variables with missing data > 30%
* imputed missing values by using either the mean or mode of those variables
* created 2 new variables, 'comorbidity score' and 'gcs_score'

# EDA 
* visualised relationships between numerical values and target variable by using boxplots
* removed explanatory variables that were strongly correlated between them
* reduced categorical variables cardinality 
* performed chi-square tests to understand the correlation between categorical/binary data and the target variable


<img width="441" alt="image" src="https://user-images.githubusercontent.com/79809854/117857638-e4dc4480-b284-11eb-869c-322c73839231.png"> <img width="680" alt="image" src="https://user-images.githubusercontent.com/79809854/117857851-2240d200-b285-11eb-8d24-a661ee3f74eb.png"> <img width="987" alt="image" src="https://user-images.githubusercontent.com/79809854/117858318-adba6300-b285-11eb-916d-15f26397872f.png">


# Model Building
* encoded categorical variables by performing dummy encoding 
* performed SMOTE to balance the minority class 
* split the data into train and tests sets with a test size of 20%
* ran 3 different algorithms used for classification problems: Logistic Regression, XGBoost and Random Forrest. 
* Fine tuned the Random Forrest and XGBoost models as these outperformed the Logistic Regression

# Model Performance 
* Random Forest Model achieved a better performance than the XGboost. 
* The model achieved an accuracy of 78% which means it predicts correctly 78% of the cases. 
* 61% recall score which means the model correctly identifies 61% of all diabetes mellitus
* 50% precision which means when it predicts diabetes mellitus as positive, it is correct 50% of the time
<img width="492" alt="image" src="https://user-images.githubusercontent.com/79809854/119718481-8952af00-be5f-11eb-8788-c0c5038b67b6.png">

# Feature Importance 
* performed feature importance with shap 
<img width="650" alt="image" src="https://user-images.githubusercontent.com/79809854/119719424-aa67cf80-be60-11eb-8e96-c2e79fb37f79.png">
<img width="650" alt="image" src="https://user-images.githubusercontent.com/79809854/119719463-b358a100-be60-11eb-9bfd-cdbe573a5413.png">




