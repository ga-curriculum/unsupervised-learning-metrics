<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Introduction to Unsupervised Learning</span>
</h1>

## Learning Objective
By the end of this lesson, students will be able to:
- Define unsupervised learning and its key characteristics.
- Differentiate between supervised and unsupervised learning.
- Identify common unsupervised learning techniques, including clustering and dimensionality reduction.

---

## What is Unsupervised Learning?
Unsupervised learning finds **hidden patterns or structures** in unlabeled data. Unlike supervised learning, it doesn't rely on labeled datasets but instead explores the inherent structure of the data to generate insights.

### **Supervised vs. Unsupervised Learning**

| Feature | Supervised Learning | Unsupervised Learning |
|---------|---------------------|---------------------|
| Data | Labeled | Unlabeled |
| Objective | Prediction & classification | Discovery & exploration |
| Common Uses | Spam detection, price prediction | Customer segmentation, anomaly detection |

<div class="mermaid">
graph LR
  A[Machine Learning] --> B[Supervised Learning]
  A --> C[Unsupervised Learning]
  B --> D["Labeled Data"]
  B --> E["Predict outcomes"]
  B --> F["Classification & Regression"]
  C --> G["Unlabeled Data"]
  C --> H["Discover patterns"]
  C --> I["Clustering & Dimensionality Reduction"]
</div>

## Common Techniques

### Clustering
Clustering groups similar data points together to **reveal inherent structures**.
- **Example:** Grouping customers based on shopping habits.
- **Common Algorithms:** K-Means, DBSCAN, Hierarchical Clustering

### Dimensionality Reduction
Reduces dataset complexity while **preserving meaningful relationships**.
- **Example:** Visualizing high-dimensional data in 2D or 3D space.
- **Common Algorithms:** PCA, t-SNE, Autoencoders.

## Let's try it out! Basic Clustering with K-Means
Let's practically understand clustering by segmenting customers based on purchasing behavior.


```python
import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

# Generate synthetic customer data
np.random.seed(42)
customer_data = np.random.rand(100, 2) * [100, 500]  # Simulate spending & frequency

# Apply K-Means Clustering
kmeans = KMeans(n_clusters=3)
kmeans.fit(customer_data)  
labels = kmeans.labels_

# Visualize the clusters
plt.figure(figsize=(8,6))
plt.scatter(customer_data[:,0], customer_data[:,1], c=labels, cmap='viridis')
plt.title('Customer Segmentation using K-Means')
plt.xlabel('Purchase Frequency')
plt.ylabel('Average Spend')
plt.show()

```

**Discuss!** Imagine you are working with a marketing agency. How might a marketer use this segmentation data to design targeted campaigns?

## Think About Your Role...
Think about clients you have worked with in the past, or are currently working with. 

Can you think of any examples where unsupervised learning would provide valuable insights?

## Key Takeaways:

- Unsupervised learning discovers hidden patterns in unlabeled data.
- Clustering and dimensionality reduction are primary unsupervised learning methods.
- K-Means is a powerful technique for customer segmentation.































