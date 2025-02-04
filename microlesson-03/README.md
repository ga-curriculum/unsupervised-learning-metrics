<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Dimensionality Reduction Techniques</span>
</h1>

## Micro‑Lesson 3: Dimensionality Reduction Techniques 🎯

### A. Principal Component Analysis (PCA) 📉

- **Concept and Intuition:**  
  PCA transforms high‑dimensional data into a lower‑dimensional space by identifying principal components that capture maximum variance.

- **Key Steps:**  
  1. 📏 **Standardize the data.**  
  2. 🏛️ **Compute the covariance matrix.**  
  3. 🧮 **Calculate eigenvalues and eigenvectors.**  
  4. 🎯 **Select top components** (e.g., capturing 90‑95% of variance).  
  5. 📊 **Project the data** onto these components.

- **Applications:**  
  - 🔍 Data visualization
  - 🎛️ noise reduction
  - 🤖 preprocessing for machine learning

### B. t‑Distributed Stochastic Neighbor Embedding (t‑SNE) 🌐

- **Concept:**  
  A non‑linear technique that preserves local structure and is used primarily for visualizing high‑dimensional data in 2D or 3D.

- **Use Cases:**  
  - 👥 Visualizing clusters in **customer segmentation** or 🧬 **gene expression data**.

- **Limitations:**  
  - ⚡ **Computationally intensive** and sensitive to parameters (perplexity, learning rate).

### C. Autoencoders 🤖

- **Overview:**  
  Autoencoders are **neural networks** that learn compressed representations of data by encoding and then reconstructing the input.

- **Key Components:**  
  - 🔒 **Encoder:** Compresses the input into a latent‑space representation.  
  - 🔓 **Decoder:** Reconstructs the original input from the compressed representation.

- **Applications:**  
  - 🏷️ Feature extraction  
  - 🚨 Anomaly detection  
  - 🖼️ Image compression

### Discussion & Activity 💡

**Hands‑On Dimensionality Reduction Activity:**  
1. 🖼️ Using a sample high‑dimensional dataset (e.g., handwritten digits), apply **PCA** to reduce dimensions and visualize the results.  
2. 📌 In small groups, compare the **PCA plot** with a **t‑SNE plot** of the same data.  
3. 🤔 Discuss the advantages and disadvantages of **linear** vs. **non‑linear** dimensionality reduction methods.  
4. 🚀 Optionally, explore an **autoencoder model** (using a tool like **TensorFlow** or **PyTorch**) and compare its **reconstruction error** to the variance explained by **PCA**.



