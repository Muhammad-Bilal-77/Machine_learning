# 🧠 Complete Machine Learning & Reinforcement Learning Portfolio

Welcome to my comprehensive Machine Learning and Reinforcement Learning repository! 

This repository serves as a masterclass portfolio, showcasing a deep understanding of data science principles ranging from extensive data wrangling and baseline statistical modeling to state-of-the-art gradient boosting, neural networks, and self-learning reinforcement agents.

Unlike generic tutorials that simply import libraries and call `.fit()`, the code in this repository focuses heavily on the underlying mathematics, system architecture, advanced metrics, and algorithm interpretability.

---

## 📂 Repository Architecture

```text
Machine_learning/
│
├── supervised_learning/
│   ├── housing_eda/                  ⭐ Flagship: End-to-End House Price Prediction Pipeline
│   ├── logistic_regression/          ⭐ Highlight: Breast Cancer Classification
│   ├── random_forest/
│   ├── xgboost/
│   └── linear_regression/
│
├── unsupervised_learning/            ⭐ Highlight: Uncovering Hidden Data Structures
│   ├── recommender_system/
│   └── clustering/
│
├── reinforcement_learning/
│   └── tic_tac_toe/                  ⭐ Flagship: Custom Q-Learning Agent
│
└── advanced_ml/
    └── neural_networks/
```

---

## ⭐ Spotlight: Core Flagship Projects

These projects form the foundational pillars of the repository, demonstrating advanced algorithm design, deep statistical exploration, and complete end-to-end Machine Learning pipelines.

### 1. Supervised Learning: End-to-End House Price Prediction Pipeline
**Location:** `supervised_learning/housing_eda/House_Price_Prediction_Model.ipynb`

This project is a massive, professional-grade Machine Learning pipeline predicting real estate prices on the Ames Housing Dataset. It demonstrates the entire Data Science lifecycle from raw data to final predictive model:
- **Deep Exploratory Data Analysis (EDA):** Uncovering hidden correlations, visualizing feature distributions, and identifying critical outliers that disrupt linear models.
- **Robust Preprocessing & Feature Engineering:** Handling complex missing values (differentiating between missing data and non-existent features), preserving hierarchical ordinal variables, and utilizing logarithmic mathematical transformations (`np.log1p`) to normalize heavy-tailed statistical distributions.
- **Algorithm Comparison Engine:** Training, tuning, and evaluating 6 different supervised learning algorithms side-by-side (Linear Regression, Ridge, Lasso, Random Forest, XGBoost, and Gradient Boosting) using RMSE, MAE, and $R^2$.
- **Final Result:** The optimal Gradient Boosting Regressor captured non-linear relationships to explain ~93% of the variance ($R^2$ = 0.9294) with a highly accurate average error of just $14,078 per home.

### 2. Reinforcement Learning: Tic-Tac-Toe Q-Learning AI
**Location:** `reinforcement_learning/tic_tac_toe/Tic_Tac_toe.ipynb`

This project demonstrates how to build an Artificial Intelligence agent entirely from scratch that learns optimal strategies without being explicitly programmed with the rules of the game. 
- **Custom Environment:** I built a custom Tic-Tac-Toe environment that acts as the physics engine and state-tracker for the AI.
- **Q-Learning Implementation:** The agent utilizes the Bellman Equation to populate a massive memory bank (a Q-Table). By mathematically balancing **Exploration** (trying random moves) and **Exploitation** (relying on known winning strategies), the AI maps out the best possible moves.
- **Self-Play:** Through thousands of hyper-speed simulated games, the AI learns from positive rewards (winning) and negative penalties (losing) to eventually achieve a flawless strategy where its worst-case scenario is a draw.

---

## 🔍 Unsupervised Learning Modules

When data lacks labels, we must rely on pure mathematics to find hidden structures, clusters, and relationships.

### Collaborative Filtering Recommender System
**Location:** `unsupervised_learning/recommender_system/Collaborative_Filtering_Advanced.ipynb`
- A User-Based Collaborative Filtering engine built from scratch using pure `numpy` Linear Algebra. 
- It calculates the **Cosine Similarity** between users' rating vectors to find mathematically identical "taste clusters." This allows the engine to predict how a user will rate an unseen movie based on peer-weighted averages.

### K-Means Clustering
**Location:** `unsupervised_learning/clustering/KMeans_Clustering.ipynb`
- A clustering algorithm built using SciPy's optimized engine to group unlabeled data. 
- The core focus here is on **Variance Normalization (Whitening)**—a critical mathematical step that ensures features on massive scales (like Income) don't overpower smaller-scaled features (like Age) in the Euclidean distance calculation.

---

## 📈 Additional Supervised Learning Modules

The supervised learning section contains heavily tuned algorithms focused on regression and classification, utilizing robust frameworks like `statsmodels` and `xgboost`.

- **Logistic Regression Classification**: A breast cancer classification model that abandons standard accuracy in favor of evaluating the **Confusion Matrix**, prioritizing the tracking of fatal False Negatives in medical data.
- **Random Forest**: Built using XGBoost's specialized API, this model prevents decision tree overfitting through mathematical **Bagging** (Bootstrap Aggregating) and **Random Subspace** feature sampling. Includes custom feature importance extraction.
- **Extreme Gradient Boosting (XGBoost)**: A state-of-the-art Kaggle-tier regression model. To prevent the gradient descent engine from memorizing the data, it features an evaluation set with **Early Stopping** and plotted learning curves to pinpoint exactly where the model peaks in intelligence.
- **Linear Regression (`statsmodels`)**: Moving beyond basic `scikit-learn` models, this module digs into statistical significance (p-values) and performs rigorous **Residual Diagnostics** to prove homoscedasticity and mathematical validity.

---

## 🧠 Advanced ML: Deep Learning

- **TensorFlow / Keras Neural Networks**: A Multi-Layer Perceptron (MLP) architecture designed to classify images of handwritten digits. 
- **Overfitting Prevention**: It features critical preprocessing (pixel scaling) and advanced layer design, explicitly utilizing **Dropout Layers** (randomly disabling 20% of neurons) to force the network to learn generalized patterns rather than memorizing exact pixels.
- **Lifecycle Diagnostics**: Includes side-by-side plots of Training Loss vs. Validation Loss across 30 epochs to visually prove the network's health and generalization ability.

---

## ⚙️ Environment Setup & Engineering Notes

This repository was specifically engineered to be resilient against strict Windows Application Control Policies (which often block standard `scikit-learn` C-extension DLLs like `_libsvm_sparse`). 

To bypass these system-level constraints while still delivering enterprise-grade performance, the architecture deliberately avoids standard library bloat in favor of robust alternatives:
- **Regression Math**: Handled via `statsmodels`.
- **Ensembles (Forests & Boosting)**: Handled entirely via the `xgboost` engine.
- **Clustering Distance Math**: Handled natively by `scipy.cluster.vq`.
- **Deep Learning**: Handled via `tensorflow`.
- **Recommender Engines**: Built natively from scratch in `numpy`.

**Dependencies Required:**
`pip install nbformat jupyter tensorflow statsmodels xgboost scipy numpy pandas matplotlib scikit-learn`
