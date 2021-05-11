# Predict Diabetes Mellitus
* Predicted whether a patient admited to ICU(Intensive Care Unit) has diabetes mellitus to help hospitals administer the appropriate medical treatment
* Cleaned the data, removed or imputed missing values, analysed relationships between variables and target variables. 
* Engineered features 
* Created a SMOTE dataset to balance the minority class 
* Optimised Xgboost model using GridsearchCV to find best parameters 

_This analysis was done as part of the WIDS (Women in Data Science) kaggle competition and represents the collaborative effort of the team I was part of._


# Data Cleaning 
* The data for this problem is provided by MIT’s GOSSIS (Global Open Source Severity of Illness Score)initiative. It contains: 180 features and the target variable 'diabetes mellitus'. 
* _Link to dataset: https://www.kaggle.com/c/widsdatathon2021/data_

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
* created SMOTE dataset to balance the minority class 
* split the data into train and tests sets with a test size of 20%
* picked XGBoost for data modelling because it performs well on imbalance datasets and can pick up well non-linear relationships

# Model Performance 
* achieved an accuracy of 86,6 on test set
* performed feature importance with shap 
<img width="493" alt="image" src="https://user-images.githubusercontent.com/79809854/117859206-9c258b00-b286-11eb-8980-b2664cd44110.png"> 
<img width="432" alt="image" src="https://user-images.githubusercontent.com/79809854/117859256-a9427a00-b286-11eb-962d-970afe60ee53.png">
<img width="705" alt="image" src="https://user-images.githubusercontent.com/79809854/117859587-1c4bf080-b287-11eb-9ec7-8835bce18c00.png">
<img width="705" alt="image" src="https://user-images.githubusercontent.com/79809854/117859419-ddb63600-b286-11eb-9799-ad94f2278e2f.png">




