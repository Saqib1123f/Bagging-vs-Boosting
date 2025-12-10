# Ensemble Learning: Bagging vs Boosting

A comprehensive machine learning project that demonstrates and compares two fundamental ensemble learning techniques: **Bagging** and **Boosting**. This project provides visual and quantitative analysis of how these methods reduce variance and bias respectively, using the classic two-moons dataset.

## 📋 Table of Contents

- [Overview](#overview)
- [Theory Background](#theory-background)
- [Features](#features)
- [Requirements](#requirements)
- [Installation](#installation)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Key Concepts](#key-concepts)
- [Results](#results)
- [Author](#author)

## 🎯 Overview

This project explores ensemble learning methods through practical implementation and visualization. It compares:

- **Bagging (Bootstrap Aggregating)**: Reduces variance by training multiple models on bootstrap samples
- **Boosting (Gradient Boosting)**: Reduces bias by sequentially training models that correct previous errors
- **Baseline Decision Tree**: Single tree classifier for comparison

The analysis includes:
- Visual decision boundary comparisons
- Performance metrics (accuracy scores)
- Learning curves showing performance vs ensemble size
- Theoretical explanations of variance and bias reduction

## 📚 Theory Background

### Bagging (Bootstrap Aggregating)

- Trains many models **independently** on bootstrap samples (sampling with replacement)
- Each model sees a slightly different dataset
- Errors average out, dramatically reducing **variance**
- Random Forest is a famous extension of bagging

### Boosting (Gradient Boosting)

- Trains models **sequentially**, not independently
- Each new model focuses on mistakes of the previous one
- In Gradient Boosting, each model fits the negative gradient of the loss
- Reduces **bias** by adding many small corrections
- Creates a strong predictor from many weak learners

### Comparison

| Method | How It Learns | What It Improves | Risk |
|--------|---------------|------------------|------|
| Bagging | Parallel learners on bootstrap samples | Variance | Less interpretable |
| Boosting | Sequential learners correcting error | Bias | Can overfit if too many estimators |

## ✨ Features

1. **Dataset Generation**: Uses the two-moons dataset (non-linear, noisy, ideal for decision boundary visualization)
2. **Baseline Model**: Single Decision Tree classifier for comparison
3. **Bagging Implementation**: BaggingClassifier with 50 estimators
4. **Boosting Implementation**: GradientBoostingClassifier with 100 estimators
5. **Visualization**: Decision boundary plots for each method
6. **Performance Analysis**: Learning curves showing accuracy vs number of estimators (1-100)

## 📦 Requirements

- Python 3.7+
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

See `requirements.txt` for specific versions.

## 🚀 Installation

1. Clone or download this repository

2. Install the required packages:

```bash
pip install -r requirements.txt
```

## 💻 Usage

1. Open the Jupyter notebook:

```bash
jupyter notebook notebook16.ipynb
```

2. Run all cells sequentially to:
   - Generate the two-moons dataset
   - Train baseline, bagging, and boosting models
   - Visualize decision boundaries
   - Generate performance comparison plots

3. Alternatively, you can run the notebook programmatically:

```bash
jupyter nbconvert --to notebook --execute notebook16.ipynb
```

## 📁 Project Structure

```
.
├── notebook16.ipynb      # Main Jupyter notebook with all code and analysis
├── requirements.txt      # Python package dependencies
└── README.md            # This file
```

## 🔑 Key Concepts

### Variance Reduction (Bagging)
- Multiple models trained on different data samples
- Predictions are averaged
- Reduces overfitting to specific training data patterns
- Results in smoother decision boundaries

### Bias Reduction (Boosting)
- Models trained sequentially, each correcting previous errors
- Focuses on hard-to-predict instances
- Reduces systematic errors
- Results in more refined, sharper decision boundaries

### Two-Moons Dataset
- Classic non-linear classification problem
- Two interleaving half-circles
- Contains noise, making it challenging for single models
- Ideal for visualizing decision boundaries

## 📊 Results

The notebook generates several visualizations:

1. **Training Data Visualization**: Scatter plot of the two-moons dataset
2. **Baseline Decision Boundary**: Single tree classifier boundary
3. **Bagging Decision Boundary**: Smoother boundary with reduced variance
4. **Boosting Decision Boundary**: Refined boundary with reduced bias
5. **Performance Comparison**: Learning curves showing accuracy improvement with ensemble size

### Expected Findings

- **Bagging**: Rapid early improvement as variance is reduced
- **Boosting**: Steady improvement as bias is reduced
- Both methods outperform single decision trees
- Different performance trajectories as ensemble size increases

## 👤 Author

**Saqib Hassan**

Machine Learning & Neural Networks Assignment  
Semester 2, 2025

---

## 📝 Notes

- All random seeds are set to 42 for reproducibility
- The notebook uses 600 samples with 0.25 noise for the two-moons dataset
- Training/test split is 70/30
- Bagging uses 50 estimators by default
- Boosting uses 100 estimators with learning rate 0.1

## 🔗 References

- Scikit-learn Documentation: [Ensemble Methods](https://scikit-learn.org/stable/modules/ensemble.html)
- Breiman, L. (1996). "Bagging predictors"
- Friedman, J. H. (2001). "Greedy function approximation: A gradient boosting machine"

