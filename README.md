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
    - train.csv: 1460 rows × 80 cols
    - test.csv: 1459 rows × 79 cols
  + Blank/Null:
    - train.csv: LotFrontage (17.74%)
    - test.csv: LotFrontage (15.56%), MSZoning (0.27%), SaleType (0.07%)
  → Fill LotFrontage by mean value by Neighborhood. Fill MsZoning, SaleType by mode
  + Zero value: LotFrontage, LotArea
  → No Zero_value were found in these columns.
  + Outliers:
    - train.csv: EnclosedPorch (14.25%), BsmtFinSF2 (11.44%), OverallCond (8.56%); ScreenPorch (7.95%); MSSubClass (7.05%)...
    - test.csv: EnclosedPorch (17.20%), BsmtFinSF2 (12.34%), ScreenPorch (9.6%); OverallCond (8.7%); MSSubClass (7.13%)...
  → No rows were dropped or transformed at this stage due to these features may represent real variations in housing data.
**D. Key Findings & Actionable Plans**

_**Key Findings**_

- 

_**Actionable Plans**_

- 

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

- 

**About Me**

Hi, I'm Navin (Bao Vy) – an aspiring Data Analyst passionate about turning raw data into actionable business insights. I’m eager to contribute to data-driven decision making and help organizations translate analytics into business impact. For more details, please reach out at:

🌐 LinkedIn: https://www.linkedin.com/in/navin826/

📂 Portfolio: https://github.com/CallmeNavin/
