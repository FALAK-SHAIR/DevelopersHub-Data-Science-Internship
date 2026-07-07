# Task 2: Customer Segmentation Using Unsupervised Learning

**DevelopersHub Corporation — Data Science & Analytics Internship (Advanced Task Set)**

## Objective
Cluster mall customers based on their spending habits and demographics, and propose marketing strategies tailored to each segment.

## Dataset
- **Mall Customers Dataset** — 200 customers, 5 columns: `CustomerID`, `Gender`, `Age`, `Annual Income (k$)`, `Spending Score (1-100)`

## Approach
1. **EDA:** Explored distributions of Age, Annual Income, and Spending Score; gender split; correlation between numeric features; pairwise relationships.
2. **Preprocessing:** No missing values. Features (`Age`, `Annual Income`, `Spending Score`) scaled with `StandardScaler` since K-Means relies on Euclidean distance.
3. **Optimal k selection:** Used the **Elbow Method** (inertia) and **Silhouette Score** across k=2–10, both pointing to **k=5**.
4. **Clustering:** Applied **K-Means** (k=5) on the scaled features.
5. **Visualization:** Plotted clusters directly on Income vs Spending Score, and also reduced all 3 scaled features to 2D using **PCA** and **t-SNE** to confirm the clusters are genuinely separable, not just an artifact of picking 2 axes.
6. **Cluster Profiling:** Computed average Age, Income, Spending Score, and % Female per cluster, and translated each profile into a concrete marketing strategy.

## Results — Cluster Profiles

| Cluster | Avg Age | Avg Income (k$) | Avg Spending Score | Count | Segment |
|---|---|---|---|---|---|
| 0 | 46.2 | 26.8 | 18.4 | 20 | Low Income, Low Spending |
| 1 | 25.2 | 41.1 | 62.2 | 54 | Low/Mid Income, High Spending (young, engaged) |
| 2 | 32.9 | 86.1 | 81.5 | 40 | High Income, High Spending (Premium/VIP) |
| 3 | 39.9 | 86.1 | 19.4 | 39 | High Income, Low Spending (untapped potential) |
| 4 | 55.6 | 54.4 | 48.9 | 47 | Average / Moderate (older, mainstream) |

Silhouette score for k=5 confirms good cluster separation and cohesion.

## Marketing Strategies by Segment
- **Premium/VIP (Cluster 2):** Loyalty programs, early access, exclusive events — protect and grow this high-value group.
- **High Income, Low Spending (Cluster 3):** Biggest untapped opportunity — investigate via surveys, personalize offers to convert latent spending power.
- **Young, High Spending (Cluster 1):** Value-conscious but highly engaged — target with discount bundles and loyalty points.
- **Low Income, Low Spending (Cluster 0):** Least profitable currently — keep marketing spend lean (email newsletters, seasonal sales).
- **Mainstream/Moderate (Cluster 4):** Standard promotions, cross-sell/up-sell, seasonal catalogues.

## Files
- `Task2_Customer_Segmentation.ipynb` — full analysis notebook (EDA → scaling → elbow/silhouette → K-Means → PCA/t-SNE visualization → cluster profiling → marketing strategy)
- `data/Mall_Customers.csv` — dataset used
- `outputs/` — all saved charts (EDA, elbow/silhouette, cluster visualizations, PCA, t-SNE)

## Tools & Libraries
pandas, numpy, matplotlib, seaborn, scikit-learn (KMeans, PCA, TSNE, silhouette_score)
