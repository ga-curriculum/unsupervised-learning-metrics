<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Clustering Techniques</span>
</h1>

## Clustering Techniques

### A. K‑Means Clustering 🔵

- **Algorithm Overview:**  
  K‑Means partitions data into a predefined number of clusters (K) by iteratively assigning points to the nearest centroid and updating the centroids based on the mean of assigned points.

- **Key Steps:**  
  1. **Initialization** 🎯: Randomly select K initial centroids.  
  2. **Assignment** 🔄: Assign each data point to the nearest centroid (using Euclidean distance, for example).  
  3. **Update** 📊: Recalculate centroids as the mean of assigned points.  
  4. **Iteration** 🔁: Repeat until centroids stabilize.

- **Characteristics:**  
  - ✅ Simple and efficient for spherical, equally sized clusters.  
  - ⚠️ Sensitive to initialization and outliers.

- **Choosing the Number of Clusters:**  
  The **Elbow Method** 📉 is commonly used—plot the Within‑Cluster Sum of Squares (WCSS) for different values of K and select the “elbow” point where improvements taper off.

### B. Hierarchical Clustering 🌳

- **Overview:**  
  Builds a hierarchy of clusters represented as a dendrogram.  
  - **Agglomerative (Bottom‑Up) ⬇️:** Start with individual points and merge clusters.  
  - **Divisive (Top‑Down) ⬆️:** Start with one cluster and split iteratively.

- **Characteristics:**  
  - 🏷️ No need to predefine the number of clusters.  
  - 🔎 Reveals relationships between clusters, but can be sensitive to noise.

### C. Density‑Based Clustering (DBSCAN) 🔶

- **Overview:**  
  DBSCAN groups data points based on density without requiring the number of clusters in advance.  
  - **Core Points** 🔵: Have a minimum number of neighbors (MinPts) within a radius (ε).  
  - **Border Points** 🟠: Lie near core points.  
  - **Noise Points** ❌: Are not part of any cluster.

- **Parameter Selection:**  
  Use a **k‑distance plot** 📈 to select an appropriate ε, and set MinPts based on domain knowledge.

- **Advantages:**  
  - 🌀 Finds clusters of arbitrary shape.  
  - 🛡️ Robust to noise.

### Discussion & Activity 💬

**Comparative Analysis Exercise:**  
Work in pairs or small groups to:  
1. 🔍 Compare the core differences between K‑Means, Hierarchical Clustering, and DBSCAN.  
2. 🏆 Discuss scenarios where each technique would be most effective (e.g., using DBSCAN for irregularly shaped clusters in geographic data).  
3. 📝 Create a table summarizing the advantages and limitations of each method.  
4. 🌍 Share a real‑world example from industries (like marketing or healthcare) where the choice of clustering algorithm significantly impacted results.



