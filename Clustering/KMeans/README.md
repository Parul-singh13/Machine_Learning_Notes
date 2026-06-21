Goal: Partition data into k clusters by minimizing the within-cluster variance — i.e., making points in the same cluster as close as possible to each other.

Algorithm (Lloyd's algorithm):

-Pick k initial centroids (often randomly, or via K-Means++ for smarter init)
-Assign each point to its nearest centroid
-Recompute centroids as the mean of points in each cluster
-Repeat assign → update until centroids stop moving (convergence)


Objective function: Minimizes the inertia (sum of squared distances from each point to its assigned centroid) — this is what's actually being optimized at each step.

Key assumptions/limitations:

Assumes clusters are spherical, similarly sized, and similar density — struggles with elongated or irregularly shaped clusters
Sensitive to initialization (can converge to a bad local minimum — why K-Means++ exists)
You must choose k in advance — done via the Elbow Method (plot inertia vs k, look for the bend) or Silhouette Score


Practical notes for interviews:

Sensitive to outliers (since it uses means) and to feature scale (always standardize/normalize features first)
Time complexity is roughly O(n·k·i·d) — scales well, which is why it's preferred over Hierarchical Clustering for large datasets
Common follow-up question: "How is it different from DBSCAN?" → K-Means needs k upfront and assumes spherical clusters; DBSCAN finds clusters of arbitrary shape and detects noise/outliers automatically without specifying k.
<img width="832" height="365" alt="image" src="https://github.com/user-attachments/assets/bb3074e3-f88f-4f69-abb8-9d18760a41d6" />
