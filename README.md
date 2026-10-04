# Machine Learning Assignment: Polynomial Regression & Bias-Variance Trade-Off

This repository contains an R-based machine learning analysis exploring polynomial regression, data simulation, training/test splits, mean squared error (MSE) comparison, and the bias-variance trade-off. 

The project was completed as part of a group assignment for Applied Mathematics[cite: 1].

---

## 📊 Project Overview & Tasks

The project is structured into several core analytical and programming tasks:

1. **Data Simulation (Task A):** Simulated $n = 200$ observations from a noisy sine wave model $y = \sin(x) + \epsilon$, where $\epsilon \sim \mathcal{N}(0, 1)$, using evenly spaced $x$ values on $[0, 10]$[cite: 1].
2. **Train/Test Split (Task B):** Randomly partitioned the data into a training set ($70\%, n = 140$) and a test set ($30\%, n = 60$) to evaluate out-of-sample generalization[cite: 3].
3. **Model Fitting (Task C):** Fitted polynomial regression models across multiple degrees ($p \in \{1, 3, 4, 7, 10, 15\}$)[cite: 4] and evaluated changes in training $R^2$[cite: 4].
4. **MSE Comparison (Task D):** Computed and contrasted training and test Mean Squared Errors (MSE) across all degrees to determine the optimal model configuration[cite: 5].
5. **Visualization (Tasks E & F):** Generated comparative plots mapping fitted polynomial curves against the true signal[cite: 6], alongside curves showing the interaction between model flexibility, training/test MSE, and the irreducible error ($\text{Var}(\epsilon) = 1$)[cite: 7, 8].
6. **Model Selection & Discussion (Task G):** Analyzed the results through the lens of the bias-variance trade-off, interpretability, and underlying data assumptions[cite: 9].

---

## 🚀 Key Findings & Conclusions

* **Flexibility vs. Error:** As model flexibility (polynomial degree) increases, training error consistently drops due to higher parameter capacity[cite: 4]. 
* **Test Performance:** The degree 15 model achieved the lowest test MSE ($\approx 0.8335$), capturing the non-linear structure effectively without a sharp spike in test variance[cite: 5, 9]. However, lower degrees (such as degree 7) offer a more practical balance between predictive accuracy and model interpretability[cite: 5].
* **Linear vs. Non-Linear Dynamics:** The analysis highlights that complex models are necessary for non-linear relationships like the sine wave; a simple linear model results in severe underfitting[cite: 3].

---

## 🛠️ Requirements & Usage

The scripts require **R**. You can run the analysis pipeline by executing the main script or notebook file:

```R
# Example snippet for data simulation and plotting model fits
set.seed(123)
n <- 200
x <- seq(0, 10, length.out = n)
eps <- rnorm(n, mean = 0, sd = 1)
y <- sin(x) + eps
