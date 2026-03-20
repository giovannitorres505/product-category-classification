# Product Category Classification - Amazon Sales Dataset

## Overview

Multiclass classification model that predicts the **product category** of an Amazon order based on its numerical features.

---

## Problem Statement

Given information about an order — such as price, discount, rating and review count — can a model correctly identify which product category it belongs to?

This is a challenging problem because numerical features alone do not strongly distinguish between categories. A book and a beauty product can have the same price, the same discount and the same rating. The model accuracy reflects this data limitation honestly.

---

## Dataset

The dataset contains **50,000 Amazon orders** across 6 product categories.

| Column | Description |
|---|---|
| `price` | Original product price |
| `discount_percent` | Discount percentage applied |
| `quantity_sold` | Quantity sold per order |
| `rating` | Product rating (1.0 to 5.0) |
| `review_count` | Number of reviews |
| `product_category` | Target — one of 6 categories |

**Categories:** Books, Electronics, Fashion, Beauty, Sports, Home & Kitchen

---

## Features Used

| Feature | Description |
|---|---|
| `price` | Original product price |
| `discount_percent` | Discount percentage applied |
| `quantity_sold` | Quantity sold |
| `rating` | Product rating |
| `review_count` | Number of reviews |

---

## Project Structure

```
product-category-classification/
│
├── product_category_classification.ipynb   # Main notebook
├── amazon_sales_dataset.csv                # Dataset
└── README.md
```

---

## Methodology

1. **Data loading and exploration** — overview of dataset structure and statistics
2. **Data cleaning** — filling missing values
3. **Target distribution** — checking class balance across 6 categories
4. **Feature distribution by category** — visualizing whether features differentiate categories
5. **Train/test split** — 80% training, 20% testing with stratification
6. **Model training** — RandomForestClassifier with 100 trees
7. **Evaluation** — accuracy, classification report, confusion matrix
8. **Feature importance** — identifying which variables most influence the prediction

---

## Algorithm

**RandomForestClassifier** — builds 100 independent decision trees on random subsets of the data. The final prediction is the majority vote across all trees, making it more robust than a single decision tree.

---

## Results

Since there are 6 categories, a random baseline would score approximately **16.7%** (1 in 6 chance). Any accuracy above that indicates the model learned real patterns from the data.

The model accuracy is modest, which is expected given that numerical features do not strongly differentiate product categories.

---

## Key Findings

- Price distributions overlap significantly across all 6 categories, confirming that price alone cannot identify a product category
- The confusion matrix reveals which categories are most frequently confused with each other
- A more accurate solution would require text-based features such as product descriptions, enabling NLP techniques to differentiate categories more effectively

---

## Limitations

This project intentionally uses only numerical features to demonstrate a real-world data science challenge: **not every problem can be solved well with the available data**. Recognizing this limitation and documenting it honestly is an important part of the data science workflow.

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
