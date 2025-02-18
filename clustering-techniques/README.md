<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Clustering Techniques</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to explain and implement the three fundamental clustering techniques.

## An Introduction to Clustering Techniques

Imagine walking into a party where you don't know anyone. Without any prior information (labels), you start grouping people based on their clothes, the language they speak, or their behavior. This is similar to how clustering works in unsupervised learning. Clustering is an unsupervised learning method used to group similar objects. In this lesson let's look at some of the fundamental clustering techniques, namely:

- K‑Means Clustering
- Hierarchical Clustering
- Density‑Based Clustering (DBSCAN)

## K‑Means Clustering

K-Means is a popular clustering technique where data points are divided into `K` clusters based on their similarities, by iteratively assigning points to the nearest centroid and updating the centroids based on the mean of assigned points.

### Key Steps

1. **Initialization**: Randomly select K initial centroids.
2. **Assignment**: Assign each data point to the nearest centroid (using Euclidean distance, for example).
3. **Update**: Recalculate centroids as the mean of assigned points.
4. **Iteration**: Repeat until centroids stabilize.

### Characteristics

- Simple and efficient for spherical, equally sized clusters.
- Sensitive to initialization and outliers.

### Choosing the Number of Clusters

The **Elbow Method** is commonly used—plot the Within‑Cluster Sum of Squares (WCSS) for different values of K and select the “elbow” point where improvements taper off.

### Implementation example

Imagine ShopSmart platform segmenting its customers into different groups based on their purchase behavior. The code below uses K-Means clustering to segment customers into two groups based on their annual income and spending score.

```python
from sklearn.cluster import KMeans
import numpy as np

# Sample data: customers with (Annual Income, Spending Score)
data = np.array([[15, 39], [16, 81], [17, 6], [18, 77], [19, 40]])

# Applying K-Means with 2 clusters
kmeans = KMeans(n_clusters=2, random_state=42)
kmeans.fit(data)

print("Cluster labels:", kmeans.labels_)
```

## Hierarchical Clustering

Unlike K-Means, hierarchical clustering builds a tree-like hierarchy of clusters, which can be cut at different levels and represented as a dendrogram. Such hierarchical clusters can be of two types:

- **Agglomerative (Bottom‑Up) :** Start with individual points and merge clusters.
- **Divisive (Top‑Down):** Start with one cluster and split iteratively.

### Characteristics:

- No need to predefine the number of clusters.
- Reveals relationships between clusters, but can be sensitive to noise.

### Implementation Example

The code below creates a dendrogram to visualize hierarchical clustering.

```python
from scipy.cluster.hierarchy import dendrogram, linkage
import matplotlib.pyplot as plt

# Sample data
data = np.array([[5, 3], [10, 15], [15, 12], [24, 10], [30, 30]])

# Hierarchical clustering
linked = linkage(data, 'ward')
dendrogram(linked)
plt.show()
```

## Density‑Based Clustering (DBSCAN)

DBSCAN groups data points based on density allowing detection of clusters of varying shapes and without requiring the number of clusters in advance.

- **Core Points**: Have a minimum number of neighbors (MinPts) within a radius (ε).
- **Border Points**: Lie near core points.
- **Noise Points**: Are not part of any cluster.

### Parameter Selection

Use a **k‑distance plot** to select an appropriate ε, and set MinPts based on domain knowledge.

### Advantages

- Finds clusters of arbitrary shape.
- Robust to noise.

### Implementation Example

The code below groups data points based on density and marks outliers.

```python
from sklearn.cluster import DBSCAN
import numpy as np

# Sample data points
data = np.array([[1, 2], [2, 2], [2, 3],
                 [8, 7], [8, 8], [25, 80]])

# Applying DBSCAN
dbscan = DBSCAN(eps=3, min_samples=2)
dbscan.fit(data)

print("Cluster labels:", dbscan.labels_)
```

## 🗣️ **Discussion Activity**: Comparative Analysis Exercise

Work in pairs or small groups to:

1. 🔍 Compare the core differences between K‑Means, Hierarchical Clustering, and DBSCAN.
2. 🏆 Discuss scenarios where each technique would be most effective (e.g., using DBSCAN for irregularly shaped clusters in geographic data).
3. 📝 Create a table summarizing the advantages and limitations of each method.
4. 🌍 Share a real‑world example from industries (like marketing or healthcare) where the choice of clustering algorithm significantly impacted results.
