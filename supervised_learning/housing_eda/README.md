# End-to-End House Price Prediction 🏡

This project is a comprehensive, end-to-end Machine Learning pipeline designed to predict house prices using the Ames Housing dataset. It demonstrates a complete Data Science lifecycle, starting from raw data and messy features, through deep Exploratory Data Analysis (EDA), advanced feature engineering, and concluding with a robust comparison of 6 different supervised learning algorithms.

## 📊 Exploratory Data Analysis (EDA) & Preprocessing Flow

The EDA in this project is meticulous and handles all common pitfalls found in real-world tabular data:

1. **Target Variable Transformation**: 
   - The original `SalePrice` was highly right-skewed.
   - Applied a logarithmic transformation (`np.log1p`) to normalize the target distribution, preventing models from being disproportionately penalized by ultra-expensive outlier homes.
2. **Missing Value Imputation**:
   - Differentiated between *true missing values* and *intentional NaNs* (e.g., `NaN` in `PoolQC` means "No Pool", not missing data).
   - Filled structural missing values logically (e.g., categorical as "None", numerical as 0 or mean/median depending on the skewness of the feature).
3. **Outlier Detection & Removal**:
   - Visualized extreme outliers using scatter plots and boxplots (e.g., homes with massive `GrLivArea` but suspiciously low `SalePrice`).
   - Safely dropped extreme outliers to improve the robustness of linear models.
4. **Feature Engineering & Skewness**:
   - Identified highly skewed numerical predictor variables.
   - Log-transformed heavily skewed features (like `LotArea`, `BsmtFinSF1`) to enforce normality.
5. **Encoding Categorical Variables**:
   - Separated nominal categories from ordinal categories.
   - Preserved the hierarchical nature of ordinal variables (e.g., `ExterQual`: Po -> Fa -> TA -> Gd -> Ex) to retain mathematical value.

## 🤖 Models Compared

To find the best predictive algorithm, the processed dataset was trained and evaluated across 6 different models. The performance metrics used were **Root Mean Squared Error (RMSE)**, **Mean Absolute Error (MAE)**, and **R-Squared ($R^2$)**.

| Model | RMSE | MAE | $R^2$ |
| :--- | :---: | :---: | :---: |
| **Gradient Boosting** | **0.1091** | **0.0799** | **0.9294** |
| Lasso Regression | 0.1143 | 0.0805 | 0.9224 |
| XGBoost | 0.1147 | 0.0813 | 0.9220 |
| Ridge Regression | 0.1183 | 0.0831 | 0.9170 |
| Random Forest | 0.1425 | 0.0958 | 0.8795 |
| Linear Regression | 0.1433 | 0.0891 | 0.8781 |

## 🏆 The Best Model

The **Gradient Boosting Regressor** emerged as the undisputed winner for this dataset. 

- **Why?** Tree-based boosting models are exceptionally well-suited for tabular data with a mix of categorical, ordinal, and continuous variables. Gradient Boosting iteratively corrects the residual errors of prior trees, allowing it to capture non-linear relationships and complex interactions between housing features (like combining the effect of `Neighborhood` and `OverallQual`) much better than standard Linear Regression.
- **Performance:** It achieved an incredible $R^2$ of **0.9294**, meaning it successfully explains ~93% of the variance in house prices. On the original price scale, it boasts a Mean Absolute Error of just **$14,078**, which is incredibly accurate given the high variance in real estate pricing.