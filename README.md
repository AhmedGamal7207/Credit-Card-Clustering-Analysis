# Credit Card Data Clustering and Analysis

## Overview

This project focuses on clustering credit card data using **K-Medoids** and **Hierarchical Clustering** techniques. The dataset includes various customer spending and credit card data, which is processed to identify clusters that can be used for customer segmentation.

## Model Architecture

The project uses the following methodologies:

### 1. **K-Medoids Clustering**
   - **Initialization**: Random initialization of centroids.
   - **Scaling**: Data is standardized using `StandardScaler` to normalize the features.
   - **KMedoids Algorithm**: The K-Medoids algorithm is used to cluster data points into `k` clusters. The number of clusters is determined by using the **Elbow Method** and **Silhouette Score** for optimal clustering performance.
   
### 2. **Hierarchical Clustering**
   - **Linkage Methods**: Four different linkage methods are used: 
     - Single
     - Complete
     - Average
     - Ward
   - **Cluster Evaluation**: The clusters are evaluated using **Silhouette Scores**.

### 3. **Outlier Handling**
   - **IQR Method**: Outliers are detected using the Interquartile Range (IQR) method.
   - **Z-Score Method**: A Z-score method is also implemented for outlier detection.

## Data Preparation

The dataset contains various features like `CREDIT_LIMIT`, `PURCHASES`, `ONEOFF_PURCHASES`, `INSTALLMENTS_PURCHASES`, etc. The data goes through the following preprocessing steps:

- **Missing Value Handling**: Rows with missing values in key columns such as `CREDIT_LIMIT` and `MINIMUM_PAYMENTS` are dropped.
- **Outlier Detection**: Outliers in `CREDIT_LIMIT` and other features are detected using the IQR method and removed from the dataset.
- **False Data Removal**: Rows where `PURCHASES` is inconsistent with `ONEOFF_PURCHASES` and `INSTALLMENTS_PURCHASES` are also removed.

## Results

### K-Medoids Clustering (K = 2 and K = 7)

- **Cluster Composition**: 
  - After applying K-Medoids, the dataset was segmented into clusters. The clusters were analyzed to observe the purchasing behavior of different customer groups.
  - The **Silhouette Score** was used to evaluate the quality of clustering for both K = 2 and K = 7.
  
### Hierarchical Clustering
- Different linkage methods were tested, including `single`, `complete`, `average`, and `ward`. The silhouette scores for each method were calculated to determine the best linkage method for clustering.

### Comparison of Clustering Methods
- The **K-Medoids** algorithm showed better performance for certain customer segments, while **Hierarchical Clustering** provided insights into hierarchical relationships between data points.

### Outlier Removal Comparison
- **Before Outlier Removal**: The dataset showed significant variance, with values such as `CREDIT_LIMIT` ranging from 50 to 30,000.
- **After Outlier Removal (IQR Method)**: The range of `CREDIT_LIMIT` was reduced to 50–13,600, and the mean and standard deviation were more consistent.
- **After Outlier Removal (Z-score Method)**: The dataset showed similar results to the IQR method, with the range reduced to 50–15,000 and slightly improved standard deviation.

## Conclusion

This analysis demonstrated that **K-Medoids** clustering is a viable method for segmenting credit card customers based on spending behavior. By using optimal clustering (K=7), the model provided valuable insights into customer profiles. The **Hierarchical Clustering** approach further validated the K-Medoids clusters and revealed potential hierarchies in the data.

Outlier removal using both the **IQR** and **Z-Score** methods helped improve the data quality, leading to more reliable clustering results. The **Silhouette Score** served as a reliable metric for evaluating cluster cohesion.

In future work, other clustering algorithms like **K-Means** or **DBSCAN** could be explored for comparison to further enhance customer segmentation strategies.
