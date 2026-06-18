# IMDB Movie Review Sentiment Analysis

A study performing **binary sentiment classification** (positive / negative) on IMDB movie reviews, comparatively evaluating seven different machine learning algorithms.

## Overview

Text preprocessing, TF-IDF vectorization, and the training and comparison of seven classification algorithms were carried out on a balanced IMDB dataset of 50,000 reviews. Logistic regression was modeled with both `statsmodels` (for statistical interpretability) and `sklearn`; hyperparameter optimization with GridSearchCV, 10-fold cross-validation, ROC/PR curves, and error analysis were applied.

## Models Used

| Group | Models | Optimization |
|-------|--------|--------------|
| Optimized | Logistic Regression · Naive Bayes · SVM | GridSearchCV |
| Baseline | MLP · CART · Random Forest · Gradient Boosting | Default parameters |

## Results

**Optimized models**

| Model | Accuracy | F1-Score | ROC-AUC |
|-------|----------|----------|---------|
| Logistic Regression | 0.9063 | 0.9067 | 0.9671 |
| SVM | 0.9049 | 0.9053 | 0.9672 |
| Naive Bayes | 0.8832 | 0.8839 | 0.9511 |

**Baseline models**

| Model | Accuracy | F1-Score | ROC-AUC |
|-------|----------|----------|---------|
| MLP | 0.8991 | 0.8991 | 0.9620 |
| Random Forest | 0.8585 | 0.8576 | 0.9341 |
| Gradient Boosting | 0.8119 | 0.8214 | 0.8993 |
| CART | 0.7216 | 0.7214 | 0.7216 |

**Logistic Regression** is recommended as the best model: in addition to achieving the highest Accuracy/F1 scores, it offers the advantage of statistically interpretable coefficients via `statsmodels` (p-value, confidence interval, Pseudo-R²).

## Workflow

1. Data loading and exploratory data analysis (EDA)
2. Text preprocessing (HTML cleaning, tokenization, stop word removal, lemmatization)
3. Word cloud and frequency analysis
4. TF-IDF vectorization (bigram, 50,000 features) and data splitting
5. Model training, optimization, and cross-validation
6. Model evaluation, comparison, and error analysis

## Libraries Used

`numpy` · `pandas` · `matplotlib` · `seaborn` · `scikit-learn` · `statsmodels` · `nltk` · `textblob` · `wordcloud` · `beautifulsoup4`

## Dataset

[IMDB Dataset of 50K Movie Reviews](https://www.kaggle.com/datasets/lakshmi25npathi/imdb-dataset-of-50k-movie-reviews)

## Usage

```bash
pip install numpy pandas matplotlib seaborn scikit-learn statsmodels nltk textblob wordcloud beautifulsoup4
jupyter notebook IMDB_Film_Yorumu_Projesi.ipynb
```

## License

This project is licensed under the MIT License.
