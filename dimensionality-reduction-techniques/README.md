<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Dimensionality Reduction Techniques</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to explain and implement some of the popular dimensionality reduction techniques.

## An Introduction to Dimensionality Reduction Techniques
Dimensionality Reduction Techniques are methods that reduce the number of features while preserving essential information. 

## Principal Component Analysis (PCA)
PCA transforms high‑dimensional data into a lower‑dimensional space by identifying principal components that capture maximum variance. Its used in algorithms that reduce features in image processing to store images efficiently. 

### Key Steps 
1. **Standardize the data.**  
2. **Compute the covariance matrix.**  
3. **Calculate eigenvalues and eigenvectors.**  
4. **Select top components** (e.g., capturing 90‑95% of variance).  
5. **Project the data** onto these components.

### Applications
- Data visualization
- noise reduction
- preprocessing for machine learning

### Implementation example
The code below reduces a high-dimensional dataset into two principal components.
```python
from sklearn.decomposition import PCA

# Applying PCA to reduce dimensions to 2
pca = PCA(n_components=2)
reduced_data = pca.fit_transform(data)

print("Reduced data:", reduced_data)
```

## t‑Distributed Stochastic Neighbor Embedding (t‑SNE)
t‑Distributed Stochastic Neighbor Embedding (t‑SNE) is a non‑linear technique that preserves local structure and is used primarily for visualizing high‑dimensional data in 2D or 3D.

### Use Cases
- Visualizing clusters in **customer segmentation** or **gene expression data**.

### Limitations 
- **Computationally intensive** and sensitive to parameters (perplexity, learning rate).

### Applications
- Visualizing customer purchase behavior to identify hidden patterns. 

### Implementation example
The code below reduces high-dimensional data to two dimensions for visualization.  
```python
from sklearn.manifold import TSNE

tsne = TSNE(n_components=2, random_state=42)
tsne_data = tsne.fit_transform(data)

print("t-SNE transformed data:", tsne_data)
```

## Autoencoders
Autoencoders are **neural networks** that learn compressed representations of data by encoding and then reconstructing the input.

### Key Components
- **Encoder:** Compresses the input into a latent‑space representation.  
- **Decoder:** Reconstructs the original input from the compressed representation.

### Applications 
- Feature extraction  
- Anomaly detection  
- Image compression
