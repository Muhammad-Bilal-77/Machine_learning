# Extreme Gradient Boosting (XGBoost): The Kaggle King

Welcome to the XGBoost section! If you've ever looked at machine learning competitions like Kaggle, you know that almost every winning solution for structured tabular data involves XGBoost.

I wanted this directory to show you how a professional sets up a Gradient Boosting model, because setting it up incorrectly almost guarantees you will overfit.

### How Does it Work? (Boosting vs Bagging)
Unlike a Random Forest (which builds hundreds of independent trees in parallel and averages them out), XGBoost builds trees **sequentially**. 
1. Tree 1 makes a prediction (and probably makes a lot of errors).
2. Tree 2 is built specifically to predict the *errors* made by Tree 1.
3. Tree 3 predicts the *errors* made by Tree 2.
This means the algorithm learns using **Gradient Descent** in function space! It literally boosts its own performance step-by-step.

### The Danger: Overfitting
Because XGBoost focuses relentlessly on fixing its own errors, if you give it too many trees, it will memorize the training dataset down to the very last outlier. The test accuracy will plummet. 

### My Implementation:
- **Early Stopping**: In the code, I intentionally set the algorithm to build up to 1,000 trees. However, I fed it an `eval_set` (test data) and told it to monitor the test error using `early_stopping_rounds=20`. The moment the test error stops going down for 20 straight rounds, the training forcibly halts! This is the gold standard for tuning boosting models.
- **Learning Curves**: I extracted the evaluation metrics from the model's memory and plotted the training curve vs the validation curve. You can visually pinpoint the exact moment the model peaks in intelligence before it begins to overfit.
- **The Dataset**: We are predicting California house prices. Notice how in the final feature importance graph, `MedInc` (Median Income) dominates everything else, proving the model successfully learned real-world socio-economic factors!