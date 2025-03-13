# Cryptocurrency Clustering Analysis with K-Means and PCA

## Overview
This project explores **K-Means clustering** on a cryptocurrency dataset, both with and without **Principal Component Analysis (PCA)** for dimensionality reduction. The goal is to identify distinct groups of cryptocurrencies based on their market data and analyze the impact of reducing feature dimensions.

## Steps Taken

### 1. **Data Loading and Preprocessing**
- Loaded cryptocurrency market data from a CSV file.
- Checked for missing values and handled them by removing NaNs.
- Standardized the data using `StandardScaler` to ensure all features had a mean of 0 and a standard deviation of 1.

### 2. **Elbow Curve Analysis for Optimal Clusters**
- Implemented the **Elbow Method** to find the optimal number of clusters (`k`).
- Compared elbow curves for:
  - **Original scaled data** (full feature set).
  - **PCA-reduced data** (dimensionality reduction to 3 principal components).

### 3. **K-Means Clustering**
- Ran **K-Means** clustering on both:
  - The **original scaled dataset**.
  - The **PCA-transformed dataset**.
- Assigned cluster labels to each cryptocurrency.

### 4. **Visualizing Cluster Results**
- Created **scatter plots** to compare clustering in:
  - Original feature space (`price_change_percentage_24h` vs. `price_change_percentage_7d`).
  - PCA-transformed space (`PC1` vs. `PC2`).
- Used **hvPlot** and **Matplotlib** to create interactive and static plots for visual analysis.

### 5. **Impact of Using PCA for Clustering**
- **Improved cluster separation**: PCA-based clustering showed more distinct groups compared to original feature clustering.
- **Faster computation**: Reducing dimensions improved K-Means efficiency.
- **Potential information loss**: Some fine-grained market features may have been lost during PCA transformation.

## Key Findings
- The **Elbow Curve** suggested that `k=4` was the optimal number of clusters.
- The **PCA-reduced data** provided **clearer and more distinct clusters**.
- Comparing **original vs. PCA clustering**, we found that PCA **enhanced interpretability** while maintaining most data variance (~89.5%).

## Future Improvements
- Perform **Hierarchical Clustering** to compare results with K-Means.
- Apply **DBSCAN** to detect outliers or hidden patterns.
- Use **TSNE or UMAP** for further dimensionality reduction in high-dimensional feature spaces.

## Tools and Libraries Used
- **Python**: `pandas`, `scikit-learn`, `matplotlib`, `hvplot.pandas`
- **Machine Learning**: `K-Means Clustering`, `PCA`, `KneeLocator`
- **Visualization**: `hvPlot`, `Matplotlib`

## Conclusion
This analysis demonstrated how **PCA can enhance K-Means clustering** by improving **efficiency and interpretability**. While PCA reduces data complexity, it must be balanced with potential information loss when clustering market data.
