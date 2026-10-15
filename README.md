# Mall Customer Segmentation: Unsupervised Learning (PR 1)

Customer segmentation on the Mall Customers dataset using three clustering algorithms: **K-Means**, **Agglomerative Hierarchical Clustering**, and **DBSCAN**.

---

## Dataset

- **Name:** Mall Customer Segmentation Data
- **Source:** [Kaggle](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)
- **File:** `Mall_Customers.csv` (200 rows, 5 columns, no missing values)
  
| Column | Description |
|---|---|
| CustomerID | Unique ID (dropped before modelling) |
| Gender | Male / Female (encoded 0/1) |
| Age | Age in years (18 to 70) |
| Annual_Income | Annual income in thousands of USD (15 to 137) |
| Spending_Score | Mall-assigned score from 1 to 100 |

---

## Project Workflow

1. **EDA:** histograms with KDE, pairplot, correlation heatmap
2. **Preprocessing:** column renaming, Gender encoding, `StandardScaler`, 2-feature subset (`Annual_Income`, `Spending_Score`)
3. **K-Means:** Elbow method, Silhouette score, centroids, cluster profiling
4. **Hierarchical:** Ward-linkage dendrogram, model fit, comparison with K-Means
5. **DBSCAN:** 4-NN distance plot, eps × min_samples grid search, noise detection
6. **Comparison:** three-panel figure, metrics table, business insights
7. **Submission:** Restart & Run All, requirements file

---

## Algorithms

### K-Means
Centroid-based algorithm that assigns each point to the nearest of *k* centres, minimising within-cluster variance (inertia). The optimal *k* was chosen using the Elbow method and Silhouette score (k = 5). Easy to interpret, but assumes roughly spherical clusters and forces every point into a cluster.

### Agglomerative Hierarchical Clustering
Connectivity-based, bottom-up algorithm using **Ward linkage**, which merges the pair of clusters that gives the smallest increase in total within-cluster variance. The dendrogram is cut at the longest uninterrupted vertical distance to choose the number of clusters (5).

### DBSCAN
Density-based algorithm controlled by `eps` (neighbourhood radius) and `min_samples` (points needed to form a dense region). It needs no *k* upfront, can find arbitrarily shaped clusters, and labels low-density points as noise. Parameters were selected using a 4-NN distance plot and a grid search (chosen: eps = `<value>`, min_samples = `<value>`).

---

### Customer Segments (K-Means)

| Segment | Suggested Marketing Action |
|---|---|
| High Income, High Spend | Loyalty rewards and VIP events |
| High Income, Low Spend | Personalised premium offers |
| Mid Income, Mid Spend | Seasonal promotions and bundles |
| Low Income, High Spend | Budget deals and installment offers |
| Low Income, Low Spend | Low-cost discount coupons |

---

## Repository Structure

```
├── pr1.ipynb
├── Mall_Customers.csv
├── requirements.txt
├── README.md
└── screenshots/
```

---

## Tools Used

Python · Jupyter Notebook · pandas · NumPy · Matplotlib · Seaborn · scikit-learn · SciPy · jinja2

## How to Run

```bash
git clone https://github.com/ranu77/UnsupervisedLearning_pr1.git
cd UnsupervisedLearning_pr1
pip install -r requirements.txt
jupyter notebook pr1.ipynb
```

Then select **Kernel > Restart & Run All**.

## Requirements

`pandas`, `numpy`, `matplotlib`, `seaborn`, `scikit-learn`, `scipy`, `jinja2`

## Author

Devanshi Kanthariya
