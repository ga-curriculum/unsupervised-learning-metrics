<h1>
  <span class="headline">Unsupervised Learning Metrics</span>
  <span class="subhead">Metrics for Dimensionality Reduction</span>
</h1>

**Learning objective:** By the end of this lesson, you'll be able to explain advanced clustering techniques such as GMMs, Spectral Clustering and Fuzzy C-Means.

## Reconstruction Error
- **Definition:** Reconstruction error quantifies the difference between the original data and the data reconstructed from its reduced representation.
- **Calculation:** Typically measured using mean squared error (MSE) or another loss function between the input and output of the dimensionality reduction method.
- **Usage:**  
  - In PCA, it can help decide how many principal components to retain.
  - In autoencoders, it guides the tuning of network architecture and training parameters.
- **Interpretation:** Lower reconstruction error indicates that the reduced representation has preserved more of the original information.

### Implementation Example
```python
# Reconstruct the original data from the reduced dimensions
reconstructed_data = pca.inverse_transform(reduced_data)

# Calculate the Reconstruction Error (Mean Squared Error)
reconstruction_error = np.mean((data - reconstructed_data) ** 2)

print("Reconstruction Error:", reconstruction_error)
```

## Explained Variance Ratio
- **Definition:** The proportion of total variance in the data that is captured by the selected components.
- **Calculation:** In PCA, each principal component has an associated eigenvalue. The ratio of an eigenvalue to the sum of all eigenvalues represents the variance explained by that component.
- **Usage:** A scree plot can help visualize the variance explained and determine the optimal number of components.
- **Trade‑Off:** Balancing a low number of dimensions with high variance retention ensures both computational efficiency and data fidelity.

### Implementation Example
The below code displays the percentage of variance captured by each principal component.
```python
print("Explained variance ratio:", pca.explained_variance_ratio_)
```

## Visual Assessment Techniques
- **Residual Plots:** Visualize the differences between original data points and their reconstructions. Consistent small residuals indicate a good reconstruction.
- **Scree Plots:** Plot the eigenvalues or variance explained by each component. The “elbow” point helps determine the optimal number of components.
- **Heatmaps:** Display the reconstruction error across different features or data points to identify which aspects of the data are poorly represented.