# Clustering on Make Moons Dataset

## Introduction

This project demonstrates clustering algorithms (**KMeans**,
**Hierarchical Agglomerative Clustering**, and **DBSCAN**) on the
classic `make_moons` dataset from scikit-learn.

The `make_moons` dataset generates two interleaving half circles. It is
a popular choice for testing clustering algorithms since the clusters
are non-linearly separable.

## Algorithms

We applied the following clustering algorithms:

1.  **KMeans** (forcing k=4 clusters)
2.  **Agglomerative Clustering** (with k=4 clusters, Ward linkage)
3.  **DBSCAN** (density-based clustering with eps=0.8, min_samples=5)

## Silhouette Score

The **Silhouette Score** measures the quality of clustering:

-   **+1** : Well-separated clusters\
-   **0** : Overlapping clusters\
-   **-1** : Poor clustering

We calculate silhouette scores for each algorithm. For DBSCAN, outliers
(-1) are excluded from the score.

### Example Results

  Algorithm            Silhouette Score (example)
  -------------------- ----------------------------
  KMeans (k=4)         0.48
  Hierarchical (k=4)   0.47
  DBSCAN (eps=0.8)     -1

## Conclusion

-   **KMeans** struggles with non-linear shapes like moons since it
    assumes spherical clusters.\
-   **Agglomerative Clustering** performs slightly better but still
    splits curved clusters unnaturally.\
-   **DBSCAN** works well for this dataset when `eps` is tuned properly,
    since it can capture non-linear shapes and ignore noise points.

This project highlights the importance of choosing clustering algorithms
based on dataset structure.
