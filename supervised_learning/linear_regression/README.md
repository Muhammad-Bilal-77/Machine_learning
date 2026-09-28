# Linear Regression Deep Dive

Hey guys! Welcome to the Linear Regression section. A lot of people think linear regression is just drawing a straight line through data, but there's a lot more going on under the hood if you want to do it right. 

In this project, I didn't just use a standard out-of-the-box library to throw data at an algorithm. I used `statsmodels` so we can really dig into the statistical significance of our features, check out p-values, and see the confidence intervals. 

### What is Linear Regression?
At its core, ordinary least squares (OLS) linear regression finds the line (or hyperplane) that minimizes the sum of the squared differences between the predicted and actual values. It's the foundational algorithm for regression tasks.

### How I Implemented It:
- **Data**: We're looking at the Diabetes dataset, predicting disease progression.
- **EDA**: First, I plotted out distributions and checked how individual features linearly correlate with the target. No blind modeling here.
- **Modeling**: I explicitly added a constant (intercept) because leaving it out forces the regression line through the origin, which usually messes up the fit. Then I ran the OLS fit.
- **Diagnostics**: I went beyond just RMSE. I plotted residuals to check for homoscedasticity (constant variance of errors), because if your residuals show a pattern, your linear model is missing something fundamental!