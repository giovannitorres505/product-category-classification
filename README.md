# Revenue Classification - Amazon Sales Dataset

## Overview

Binary classification model that predicts whether an Amazon order will generate **high or low revenue**, based on product characteristics available before the sale.

---

## Problem Statement

Instead of predicting the exact revenue value (regression), this project frames the problem as a binary classification task:

- `1` = **High Revenue** — order total is above the dataset mean (~$657)
- `0` = **Low Revenue** — order total is below the dataset mean

This is useful in real business scenarios where a quick signal ("will this order be profitable?") is more actionable than an exact number.

---

## Dataset

The dataset contains **50,000 Amazon orders** with product and customer information.

| Column | Description |
|---|---|
| `price` | Original product price |
| `discount_percent` | Discount percentage applied |
| `rating` | Product rating (1.0 to 5.0) |
| `review_count` | Number of reviews |
| `total_revenue` | Total revenue generated (used to create the target) |

---

## Features Used

| Feature | Reason for inclusion |
|---|---|
| `price` | Higher price tends to influence revenue |
| `discount_percent` | Discounts affect the final amount paid |
| `rating` | Customer satisfaction may correlate with purchase volume |
| `review_count` | Popularity indicator |

**Note:** `quantity_sold` was intentionally excluded. Since `total_revenue = price * (1 - discount/100) * quantity_sold`, including it would allow the model to reconstruct the target mathematically, causing **data leakage** and artificially perfect results.

---

## Project Structure

```
revenue-classification/
│
├── product_category_classification.ipynb   # Main notebook
├── amazon_sales_dataset.csv                # Dataset
└── README.md
```

---

## Methodology

1. **Data loading and exploration** — overview of the dataset structure and statistics
2. **Data cleaning** — filling missing values
3. **Target creation** — labeling orders as high (1) or low (0) revenue based on the mean
4. **Class distribution check** — ensuring no severe class imbalance
5. **Train/test split** — 80% training, 20% testing with stratification
6. **Model training** — RandomForestClassifier with 100 trees
7. **Evaluation** — accuracy, precision, recall, F1-score, confusion matrix
8. **Feature importance** — identifying which variables most influence the prediction

---

## Algorithm

**RandomForestClassifier** — builds 100 independent decision trees on random subsets of the data. The final prediction is the majority vote across all trees, making it more robust and less prone to overfitting than a single decision tree.

---

## Results

| Metric | Score |
|---|---|
| Accuracy | ~75.6% |
| Precision | ~68.2% |
| Recall | ~75.1% |
| F1-Score | ~71.5% |

The model correctly classifies approximately 3 out of every 4 orders. The remaining errors are expected given that only 4 features are used, without direct access to quantity sold.

---

## Key Findings

- `price` is the most important feature for predicting revenue class
- `discount_percent` has moderate influence on the classification
- `rating` and `review_count` contribute less, suggesting that popularity alone does not determine revenue level
- The model performs better on low revenue orders than high revenue orders

---

## Technologies Used

- Python 3
- Pandas
- Seaborn
- Matplotlib
- Scikit-learn

---

## How to Run

1. Clone the repository
2. Place `amazon_sales_dataset.csv` in the project folder
3. Open `product_category_classification.ipynb` in Jupyter Notebook or Google Colab
4. Run all cells in order
