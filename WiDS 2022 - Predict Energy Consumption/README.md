# WiDS 2022 Predict Building Energy Consumption 

This year WiDS challenge was to predict building energy consumption to help policymakers target retrofitting efforts to maximize emissions reductions.
The WiDS Datathon dataset was created in collaboration with Climate Change AI (CCAI) and Lawrence Berkeley National Laboratory (Berkeley Lab) and contains data around weather temperatures, building types, sector, year, energy star rating and others. 

Competition link to learn more: https://www.kaggle.com/competitions/widsdatathon2022 

# Project Summary 
- Built a regression model to predict building energy consumption
- Performed data cleaning to ensure data robustness and relevancy for the model
- Performed feature engineering, derieved new features such as a new building type with higher energy star rating to differente it from the rest of the facility types
- Measured model performance by using the RMSE score

## Data Cleaning and Feature Engineering
- removed variables with missing values > 65%
- imputed missing values with the mean of each variable
- derived new features such as a new type of building
- analysed relationships between variables and target variables
- removed multicollinear variables
- performed log transformation on numerical skewed data

## Exploratory Data Analysis
- visualised relationships between categorical data types and target variable (Fig. 1)
- observed numerical variables'distribution (Fig. 2)
- visualised relationships between numerical variables and target variable (Fig. 3)

<img width="906" alt="image" src="https://user-images.githubusercontent.com/79809854/160152406-579fbbe1-f917-48f4-9a26-8003ec2120c2.png"> (Fig. 1)

<img width="1072" alt="image" src="https://user-images.githubusercontent.com/79809854/160151774-a0bb2b69-efbe-45d0-9664-2df618cd3a4d.png"> (Fig. 2)

<img width="1604" alt="image" src="https://user-images.githubusercontent.com/79809854/160151889-c80a4560-5497-4fa9-baa3-c87805cd7e2e.png"> (Fig. 3)

## Model Building
- encoded categorical variables by performing label encoding 
- performed feature scaling
- split the data into train and tests sets with a test size of 20%
- applied a Linear regression and Light GBM algorithm
- fine tuned the Light GBM algorithm as this outperformed the linear regression

## Model Performance 
* the Light GBM model achieved a RMSE score of 36.98
<img width="397" alt="image" src="https://user-images.githubusercontent.com/79809854/160155332-bad39242-d3e8-4459-b114-77e8fae0fcc0.png">
(Picture with model performance before tuning)

## Feature Importance 
* performed feature importance with shap 
<img width="607" alt="image" src="https://user-images.githubusercontent.com/79809854/160155533-21d9f91a-22a0-4b84-8fce-5b2e34a9f219.png">
<img width="591" alt="image" src="https://user-images.githubusercontent.com/79809854/160155613-9d8151bb-e71e-468f-8abc-2bf13ec2d140.png">

# Resources 
- https://www.kaggle.com/code/usharengaraju/wids2022-lgbm-starter-w-b 
- https://www.kaggle.com/code/angiengkh/wids-2022-eda-feature-engineering 
- https://www.analyticsvidhya.com/blog/2021/05/dealing-with-missing-values-in-python-a-complete-guide/ 
- https://github.com/michevan/WIDS-Google/blob/main/colab_notebooks/template_datathon_with_solution.ipynb 
