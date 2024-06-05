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
- `min_samples`: determines the number of **neighboring points** we require to consider in order for a point to be part of a cluster

### More details on DBSCAN
There are three kinds of points.
- **Core points** are the points that have at least `min_samples` points within a distance of `eps`
- **Border points** are connected to a core point. They are within a distance of eps to a core point but they have fewer than `min_samples` points within a distance of `eps`.
- **Noise points** are the points which do not belong to any cluster. In other words, the points which have less than `min_samples`points within distance `eps` of the starting point are noise points.