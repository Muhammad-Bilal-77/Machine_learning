# Logistic Regression Explained

Hey! Welcome to the Logistic Regression project. This is arguably the most famous binary classification algorithm in the world. 

I've written the code here to be super clean and easy to follow, but I made sure it actually holds immense value by focusing on the right metrics. 

### What is Logistic Regression?
While "regression" is in the name, it's actually used for classification! It takes the same math as a linear regression line, but passes it through a "Sigmoid Function" (an S-shaped curve). This mathematically forces the output to be a number exactly between 0.0 and 1.0. 
We interpret that number as a **probability**. If the model outputs `0.85`, it means it is 85% confident the tumor is benign.

### How I Built It:
- **The Data**: We are looking at breast cancer tumors. It's a binary problem: it's either Malignant (0) or Benign (1).
- **Easy but Valuable Code**: I intentionally selected just 3 key features (`mean radius`, `mean texture`, `mean smoothness`). Feeding 30 features into a basic logit model often causes multicollinearity crashes, so by keeping it simple, the code runs perfectly and is easy to understand.
- **Visual Evidence**: I plotted a histogram showing how Malignant tumors are visibly much larger in radius than Benign ones. The model uses this mathematical separation to learn!
- **Evaluation**: Accuracy is dangerous in medicine. If a model is 90% accurate but misses all the actual cancer cases, it's a terrible model! I implemented a clear **Confusion Matrix** so we can explicitly track our False Positives and False Negatives.