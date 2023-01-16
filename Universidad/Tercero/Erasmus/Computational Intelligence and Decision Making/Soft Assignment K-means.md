#Theory/AI #Laboratory/AI 
# Introduction
K-means is mainly used for [[Clustering]] but have other applications such as data compression, feature extraction, series modeling or anomaly detection. In this unit we are going to study the softf assignement k-means, eventough there are other k-means.

# How It works
- Input
	- Set of elements
	- Number of clusters

The steps followed are:
1. Select K initial centers of clusters .
2. Assign elements to closest centroids
3. Recalculate centroids
4. Repeat 2 and 3 until algorithm converges.

# How to evaluate the simmilarity
The simmilarity is usually checked using the Euclidean distance which is obtained by
$$d_{j}= \sqrt{\sum_{i=1}{(X_i-C_i^j)^2}}$$
From this we should take the shortest distance

# How to choose the number of clusters
The elbow method is a heuristic used for clustering which is based in plotting the cost variation as a function in comparision to the clusters. And picking the elbow of the curve as the optimal number of clusters.
![[Pasted image 20230103190732.png]]
The left is an acceptable elbow method as we can see where the slope changes the most. However the second one its inexact.

![[Pasted image 20230103191106.png]]
Note that the sum of weights of a point equals to 1
