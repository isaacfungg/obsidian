***
### DBSCAN introduction
- DBSCAN is a density-based clustering algorithm.
- Intuitively, it's based on the idea that **clusters form dense regions** in the data and so it works by **identifying "crowded" regions** in the feature space.
- It can address some of the limitations of K-Means we saw above.
    - It does **not require** the user to **specify the number of clusters** in advance.
    - It can identify **points** that are **not part of any clusters**.
    - It can capture **clusters of complex shapes**.

### Two main hyperparameters

- `eps`: determines what it means for points to be "close"
- `min_samples`: determines the number of **neighbouring points** we require to consider in order for a point to be part of a cluster

### More details on DBSCAN
There are three kinds of points.
- **Core points** are the points that have at least `min_samples` points within a distance of `eps`
- **Border points** are connected to a core point. They are within a distance of eps to a core point but they have fewer than `min_samples` points within a distance of `eps`.
- **Noise points** are the points which do not belong to any cluster. In other words, the points which have less than `min_samples`points within distance `eps` of the starting point are noise points.

![[Pasted image 20240607101646.png]]
- Increasing `eps` (left to right in the plot above) means more points will be included in a cluster.
    - `eps` = 1.0 either creates more clusters or more noise points, whereas eps=3.0 puts all points in one cluster with no noise points.
- Increasing `min_samples` (top to bottom in the plot above) means points in less dense regions will either be labeled as their own cluster or noise.
    - `min_samples=2`, for instance, has none or only a fewer noise points whereas `min_samples=5` has several noise points.

### Evaluating DBSCAN clusters
- We **cannot** use the **elbow method** to examine the goodness of clusters created with DBSCAN.
- But we **can** use the **silhouette method** because it's **not dependent** on the idea of **cluster centers**.