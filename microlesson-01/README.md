<h1>
  <span class="headline">[Unsupervised Learning & Metrics]</span>
  <span class="subhead">Microlesson 01</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to tktk
1. Understand the fundamental principles and characteristics of unsupervised learning.
2. Differentiate between clustering and dimensionality reduction techniques and identify when to use each.
3. Explore and apply popular clustering algorithms, such as K-Means, Hierarchical Clustering, DBSCAN, and Gaussian Mixture Models.
4. Understand dimensionality reduction techniques, including Principal Component Analysis (PCA), t-SNE, and autoencoders.
5. Evaluate the performance of unsupervised learning models using appropriate metrics, such as silhouette score, inertia, and reconstruction error.
6. Apply unsupervised learning techniques to real-world problems, including customer segmentation, anomaly detection, and data visualization.
7. Interpret and assess the results of dimensionality reduction for feature selection, visualization, and noise reduction in machine learning workflows.


## **1. Unsupervised Learning**

Unsupervised learning is a machine learning paradigm where the algorithm learns patterns and structures from unlabeled data. Unlike supervised learning, there are no predefined labels or outcomes, and the model's goal is to organize or summarize the data in a meaningful way.

### **Key Characteristics of Unsupervised Learning**
- **No Labels:** Works with datasets that lack labels or target variables.
- **Pattern Discovery:** Focuses on identifying inherent patterns, clusters, or structures in the data.
- **Exploratory Nature:** Primarily used for data exploration, preprocessing, or to gain insights about the dataset.
- **Real-World Application:** Often used in situations where labeled data is unavailable or expensive to generate.

---

### **1.1 Popular Techniques**

#### **1.1.1 Clustering**

Clustering is a fundamental unsupervised learning technique that involves grouping data points into clusters, where each cluster contains data points that are more similar to each other than to those in other clusters.

**Key Elements of Clustering:**
- **Similarity Metrics:** Measures such as Euclidean distance, cosine similarity, or Manhattan distance are used to determine how closely related two data points are.
- **Cluster Centroids:** Each cluster is represented by a centroid, a central point summarizing the cluster.
- **Cluster Shape:** Different clustering algorithms can handle varying shapes and densities of clusters.

**Key Clustering Algorithms:**

1. **K-Means Clustering**
   ![k-means Clustering](https://git.generalassemb.ly/modular-courses/ai-solution-architect-deloitte-ENT/blob/main/_images/Screenshot%202025-01-21%20115214.png)
   [Source](https://www.researchgate.net/publication/328743729_Examining_the_Performance_of_K-Means_Clustering_Algorithm)
   
   ![ED]((https://git.generalassemb.ly/modular-courses/ai-solution-architect-deloitte-ENT/blob/main/_images/Screenshot%202025-01-21%20120339.png)
   
   [Source](https://www.researchgate.net/publication/351076785_Hierarchical_Clustering_A_Survey)
   - Partitions data into ( k ) clusters based on the distance to cluster centroids.
   - Iterative process:
     - Assign data points to the nearest cluster centroid.
     - Update centroids based on the mean of assigned points.
   - **Advantages**:
     - Simple and computationally efficient for large datasets.
   - **Limitations**:
     - Requires predefined ( k ) (number of clusters).
     - Sensitive to initialization and outliers.

3. **Hierarchical Clustering**:
   ![Hierarchical Clustering](https://git.generalassemb.ly/modular-courses/ai-solution-architect-deloitte-ENT/blob/main/_images/Screenshot%202025-01-21%20120130.png)
   
   [Source](https://www.researchgate.net/publication/351076785_Hierarchical_Clustering_A_Survey)
   
   - Builds a tree-like hierarchy of clusters (dendrogram).
   - Two Types:
     - **Agglomerative (Bottom-Up):** Starts with each point as its own cluster and merges clusters iteratively.
     - **Divisive (Top-Down):** Starts with all points in one cluster and splits them iteratively.
   - **Advantages**:
     - Does not require specifying ( k ) upfront.
   - **Limitations**:
     - Computationally expensive for large datasets.

5. **DBSCAN (Density-Based Spatial Clustering of Applications with Noise)**

    [DBSCAN](https://git.generalassemb.ly/modular-courses/ai-solution-architect-deloitte-ENT/blob/main/_images/Screenshot%202025-01-21%20142538.png)

    [Source](https://www.researchgate.net/publication/342141592_A_Review_of_Super-Resolution_Single-Molecule_Localization_Microscopy_Cluster_Analysis_and_Quantification_Methods)
   - Groups data points based on density, identifying dense regions as clusters and low-density points as noise.
   - **Advantages**:
     - Handles clusters of arbitrary shape.
     - Robust to noise and outliers.
   - **Limitations**:
     - Struggles with clusters of varying densities.

7. **Gaussian Mixture Models (GMMs)**:
   ![GMMs](https://git.generalassemb.ly/modular-courses/ai-solution-architect-deloitte-ENT/blob/main/_images/Screenshot%202025-01-21%20144821.png)
[Source(https://www.researchgate.net/publication/342408942_Coverage_Path_Planning_with_Track_Spacing_Adaptation_for_Autonomous_Underwater_Vehicles)
   - Assumes data is generated from a mixture of Gaussian distributions.
   - Provides probabilistic cluster assignments.
   - **Advantages**:
     - Handles overlapping clusters effectively.
   - **Limitations**:
     - Computationally expensive; sensitive to initialization.

---

#### **1.1.2 Dimensionality Reduction**

Dimensionality reduction techniques simplify datasets by reducing the number of features while retaining the most important information. This is crucial when working with high-dimensional data, which can lead to overfitting and high computational costs.

**Key Elements of Dimensionality Reduction:**
- **Feature Extraction:** Combines or transforms features to create a reduced representation.
- **Feature Selection:** Identifies and keeps the most relevant features.
- **Preservation of Information:** Balances reducing dimensions while retaining the structure or variance in data.

**Key Dimensionality Reduction Techniques:**

1. **Principal Component Analysis (PCA)**:
   - Identifies the directions (principal components) where the data varies the most.
   - Projects the data onto a lower-dimensional space defined by these components.
   - **Advantages**:
     - Simple, interpretable, and effective for linear relationships.
   - **Limitations**:
     - Struggles with non-linear relationships in data.

2. **t-SNE (t-Distributed Stochastic Neighbor Embedding)**:
   - Non-linear technique for visualizing high-dimensional data in 2D or 3D.
   - Preserves local relationships, making clusters visually distinct.
   - **Advantages**:
     - Excellent for exploratory data analysis and visualization.
   - **Limitations**:
     - Computationally expensive; sensitive to hyperparameters.

3. **Autoencoders**:
   - Neural networks trained to reconstruct input data after compressing it into a lower-dimensional latent space.
   - **Advantages**:
     - Captures non-linear relationships and can be fine-tuned for specific tasks.
   - **Limitations**:
     - Requires significant data and tuning.

4. **UMAP (Uniform Manifold Approximation and Projection)**:
   - Preserves both global and local data structures in dimensionality reduction.
   - Faster alternative to t-SNE with similar visual clarity.

---

## **2. Metrics for Evaluating Unsupervised Learning**

Evaluating unsupervised models can be challenging since no ground truth is available. Metrics assess how well the model organizes, reduces, or summarizes the data.

---

### **2.1 Metrics for Clustering**

1. **Silhouette Score**:
   - Measures how well a data point fits within its assigned cluster compared to other clusters.
   - **Range**: -1 (poor clustering) to +1 (good clustering).

2. **Inertia (Within-Cluster Sum of Squares)**:
   - Indicates the compactness of clusters by summing squared distances of points to their centroids.
   - **Lower inertia** suggests tighter, more defined clusters.

3. **Calinski-Harabasz Index**:
   - Ratio of between-cluster variance to within-cluster variance.
   - **Higher values** suggest well-defined clusters.

4. **Davies-Bouldin Index**:
   - Measures the average similarity between each cluster and its most similar cluster.
   - **Lower values** indicate better-defined clusters.

5. **Dunn Index**:
   - Ratio of the minimum inter-cluster distance to the maximum intra-cluster distance.
   - **Higher values** indicate better-separated clusters.

---

### **2.2 Metrics for Dimensionality Reduction**

1. **Reconstruction Error**:
   - Measures how accurately the reduced representation can reconstruct the original data.
   - **Lower values** indicate minimal information loss.

2. **Explained Variance Ratio**:
   - In PCA, measures the amount of variance retained by each principal component.
   - **Higher values** indicate better variance retention.

3. **Visualization Quality**:
   - For t-SNE or UMAP, clarity and separability of clusters in the visualization are evaluated qualitatively.

---

## **3. Practical Applications of Unsupervised Learning**

### **3.1 Clustering Applications**
1. **Customer Segmentation**:
   - Groups customers by behavior, enabling targeted marketing strategies.
2. **Anomaly Detection**:
   - Identifies unusual patterns in data, such as fraud detection or system faults.
3. **Document Organization**:
   - Groups similar text documents for easier categorization.

### **3.2 Dimensionality Reduction Applications**
1. **Data Visualization**:
   - Enables understanding of high-dimensional data by projecting it into 2D/3D for analysis.
2. **Feature Selection**:
   - Reduces redundant features for machine learning pipelines.
3. **Noise Reduction**:
   - Simplifies data by removing noise, improving model accuracy.

---

