<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Metrics for Evaluating Clustering Models</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to describe internal, external, stability, and scalability metrics for evaluating clustering quality and performance.

## An Introduction to Evaluating Clustering Models
Clustering is used by many programmes, including segmentation, pattern recognition, search engines like Google, and extra. But many clustering methods do not tell us what the “optimal” number of clusters is. Thus, it is on us to determine the “optimal” number of clusters and their quality. Otherwise, our clustering might lead to wrong decisions. Our clustering algorithm must give us clusters with a **high intra-cluster (within-cluster) similarity** and a **low inter-cluster (between-cluster) similarity**. In other words, we want dense clusters with a great distance between clusters.

## Internal Metrics
Internal metrics are crucial when ground truth labels are not available. They provide a way to assess the quality of clustering based on the attributes of the data itself. The internal cluster metrics can be used to determine the “optimal” number of clusters.

### 1. Silhouette Score
The Silhouette Score measures how similar a data point is to its own cluster compared to other clusters.

#### Calculation 
For each data point, compute:
- *a*: Average distance to all other points in the same cluster.
- *b*: Average distance to all points in the nearest (different) cluster.
- The Silhouette Score for that point is:  
    \[
    s = \frac{b - a}{\max(a, b)}
    \]

#### Interpretation
- **1️⃣:** Data points are well‑matched to their own cluster and far from other clusters.
- **0️⃣:** Clusters are overlapping.
- **Negative Values:** Data points may be misclassified.

#### Usage
Often used to determine the optimal number of clusters by comparing average silhouette scores for different K values.

#### Implementation Example
```python
from sklearn.metrics import silhouette_score
score = silhouette_score(data, kmeans.labels_)
print("Silhouette Score: ", score)
```


### 2. Davies‑Bouldin Index (DBI)
The DBI evaluates clustering quality by comparing intra‑cluster distances (compactness) with inter‑cluster distances (separation).

#### Calculation 
For each cluster, compute the ratio of the sum of average distances within the cluster to the distance between cluster centers; then average over all clusters.

#### Interpretation 
Lower DBI values indicate clusters that are compact and well‑separated.

#### Usage  
Helps compare different clustering algorithms or parameter choices.

#### Implementation Example
```python
from sklearn.metrics import davies_bouldin_score   
dbi = davies_bouldin_score(data, kmeans.labels_)   
print("Davies‑Bouldin Index: ", dbi)
```


## External Metrics
When ground truth labels are available, external metrics can provide a more objective measure of clustering performance. External cluster metrics can be used to determine the right clustering method.

### 1. Rand Index (RI)
Measures the similarity between the clustering results and a ground truth classification. It considers all pairs of data points and checks whether they are assigned in the same or different clusters in both the predicted and true labels.

#### Implementation Example
```python
from sklearn.metrics import rand_score   
ri = rand_score(data, kmeans.labels_)   
print("Rand Index: ", ri)
``` 

### 2. Adjusted Rand Index (ARI) 
Adjusts the RI to account for chance, providing a more robust measure. ARI values range from -1 to 1, with 1 representing perfect agreement.

#### Implementation Example
```python
from sklearn.metrics import adjusted_rand_score   
ari = adjusted_rand_score(data, kmeans.labels_)   
print("Adjusted Rand Index: ", ari)   
```

### 3. Mutual Information
A measure of the similarity between two labels of the same data is called mutual information between two clusters. In other words, it is employed to compare the mutual information between the anticipated model label and the real label target.

#### Implementation Example
```python
from sklearn.metrics import mutual_info_score   
mis = mutual_info_score(data, kmeans.labels_)  
print("Mutual Information: ", mis)   
```

### 4. Purity
Evaluates the extent to which clusters contain only a single class. It is calculated by assigning each cluster to the class which is most frequent in that cluster and then computing the overall accuracy.

### 5. F‑Measure
Combines precision and recall for each cluster. This metric is particularly useful when dealing with imbalanced datasets.

## Stability Analysis
Stability analysis assesses whether the clustering solution is robust to variations such as random initialization or small changes in the dataset.
#### Techniques
- Run the clustering algorithm multiple times.
- Use metrics like ARI or Normalized Mutual Information (NMI) to compare the consistency of cluster assignments.

## Scalability Metrics
Scalability metrics are critical when choosing clustering algorithms for real‑time applications or big data scenarios.
- **Time Complexity:** How the algorithm’s runtime increases with the number of data points.
- **Memory Usage:** The amount of memory required to store the data and intermediate computations.

## 🗣️ **Discussion Activity**
ShopSmart is leveraging clustering models to improve their customer segmentation and optimize marketing strategies. They are currently evaluating different clustering models and need your expertise to ensure they select the most effective method using metrics such as Silhouette Score, Davies-Bouldin Index, and external metrics like Purity or Adjusted Rand Index.

### Discussion Questions:
1. **Silhouette Score in Action:** How would you explain to ShopSmart the significance of a Silhouette Score for determining the optimal number of customer clusters in their segmentation efforts? Can you think of any scenarios where overlapping clusters might affect this score?

2. **Davies-Bouldin Index Insights:** ShopSmart is looking for clusters with strong internal cohesion and clear separation. How would you describe the value of the Davies-Bouldin Index in helping them evaluate clustering quality?

3. **Using External Metrics:** If ShopSmart has ground truth labels for some customer data, how could metrics like Adjusted Rand Index or Purity provide a more comprehensive evaluation compared to internal metrics?

4. **Choosing Metrics for ShopSmart:** Considering ShopSmart's goals of better segmentation and marketing, which clustering evaluation metrics would you prioritize, and why? What additional insights could visual tools like t-SNE provide during the process?