# P17_House-Prices-Analysis

**VERSION 1 - Predictive Analysis**

**A. Project Overview**

- This project aims to build predictive models using the train dataset in order to estimate house sale prices in the test dataset.

**B. Dataset Information**

_**Source**_

- House Prices - Advanced Regression Techniques (from Kaggle)
- https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques

**C. Methodology**

- Data Cleaning:
  + Column Type:
  + Blank/Null:
  → Fill LotFrontage by mean value by Neighborhood. Fill MsZoning, SaleType by mode
  + Zero value: LotFrontage, LotArea
  → No Zero_value were found in these columns.
  + Outliers:
- Build Model:
  + Define x, y:
    - y: SalePrice
    - x: By correlation with other columns:
      + Numeric columns
      + Category columns:
        - One-hot encoding with non-rank columns: 'MSZoning', 'Street', 'LotShape', 'LandContour', 'Utilities', 'LotConfig', 'LandSlope', 'BldgType', 'HouseStyle', 'RoofStyle', 'RoofMatl', 'MasVnrType', 'Foundation', 'Heating', 'CentralAir', 'Electrical', 'GarageType', 'GarageFinish', 'PavedDrive', 'MiscFeature', 'SaleCondition'
        - Mapping with rank columns: 'ExterQual', 'ExterCond', 'BsmtQual', 'BsmtCond', 'BsmtExposure', 'BsmtFinType1', 'BsmtFinType2', 'HeatingQC', 'KitchenQual', 'Functional', 'FireplaceQu', 'GarageQual', 'GarageCond', 'PoolQC', 'Fence'
   + Standard Scaler
   + Train Test split
   + Linear Regression
   + Random Forest Regressor
   + XGBoost Regressor
- Predict SalePrice

**D. Key Findings & Actionable Plans**

_**Key Findings**_

- Linear Regression Result:
  + MAE: 21255.91
  + RMSE: 34735.52
  + R2 Score: 0.84
  + MAPE: 12.16%
 → On average, the model’s predictions deviate by about 12% from the actual house sale prices.
 → An R² of 0.84 indicates that the selected input features explain 84% of the variance in house prices, showing that the chosen predictors are meaningful. However, the relatively high MAE and RMSE values suggest that the model still struggles with houses at extreme price ranges, leading to larger absolute errors
 → Although the model provides coefficients, due to potential multicollinearity and missing values, we do not deeply interpret them. The focus is on overall model performance metrics (R², MAE, RMSE, MAPE)
- Random Forest Regressor Result:
  + MAE: 18052.54
  + RMSE: 31999.29
  + R2 Score: 0.87
  + MAPE: 11.26%
 → On average, the model's predictions deviate also by about 11.26% from the actual houses sale prices, which is lower than Linear Regression
 → R2 score is also higher compared to Linear Regression showing that Random Forest captures more complex relationship between features and sale price
 → MAE is also lower as well, meaning fewer errors on average. However, when outliers is included, the RMSE becomes higher, since Random Forest tends to overfit extreme cases.
- XGBoost Regressor Result:
  + MAE: 16692.83
  + RMSE: 28005.09
  + R2 Score: 0.9
  + MAPE: 10.05%
 → On average, the model’s predictions deviate by about 10.05% from the actual prices (MAPE), the lowest error among the three models.
 → The R² Score (~0.90) indicates that XGBoost captures the most complex and non-linear relationships between features and house prices compared to Linear Regression and Random Forest.
 → Both MAE and RMSE are also the lowest, confirming that XGBoost not only reduces average errors but also handles outliers better than the other two models.

_**Actionable Plans**_

- Prioritize XGBoost as the main model for price prediction due to its balance of accuracy and robustness (Result file: predictive_test_file.csv)
- Prioritize XGBoost as the primary model for predicting house sale prices, given its strong balance between accuracy (lowest MAE, RMSE, MAPE) and robustness (highest R²).
  + Leverage model ensemble by combining the predictive outputs from Linear Regression, Random Forest, and XGBoost.
  + Assign importance weights to each model based on their performance.
  + Use a meta model (any model for regression) trained on these predictions to generate the final house price prediction.

**E. Appendix**

Outliers Check Result

| train.csv Column | Outlier % | test.csv Column | Outlier % |
|------------------|-----------|-----------------|-----------|
| EnclosedPorch    | 14.25     | EnclosedPorch   | 17.20     |
| BsmtFinSF2       | 11.44     | BsmtFinSF2      | 12.34     |
| OverallCond      | 8.56      | ScreenPorch     | 9.60      |
| ScreenPorch      | 7.95      | OverallCond     | 8.70      |
| MSSubClass       | 7.05      | MSSubClass      | 7.13      |
| MasVnrArea       | 6.58      | MasVnrArea      | 6.99      |
| LotFrontage      | 6.03      | LotFrontage     | 6.85      |
| BsmtHalfBath     | 5.62      | BsmtHalfBath    | 6.37      |
| OpenPorchSF      | 5.27      | OpenPorchSF     | 5.41      |
| LotArea          | 4.73      | TotalBsmtSF     | 4.18      |

**F. Further Version**

- Verson 2: Combine the results of 3 model and use a meta model to predict SalePrice in df2 (test.csv)

**About Me**

Hi, I'm Navin (Bao Vy) – an aspiring Data Analyst passionate about turning raw data into actionable business insights. I’m eager to contribute to data-driven decision making and help organizations translate analytics into business impact. For more details, please reach out at:

🌐 LinkedIn: https://www.linkedin.com/in/navin826/

📂 Portfolio: https://github.com/CallmeNavin/
