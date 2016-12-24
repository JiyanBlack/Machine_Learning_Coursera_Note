# Unsupervised Learning
Data have no lable, only X set, no y. Find some structure from the data.  
Application:  
  * Market segmentation
  * Social network analysis
  * Organize computer clusters
  * Astronomical data analysis
## Clustering

### K-means
* Steps:
  1. Initialize k cluster centroids
  2. Assign points to the cluster centroids
  3. Move the cluster centroids according the grouped points
  4. repeat 2-3 until the cluster centroids stop moving
  5. get different k groups.
* Input: k(number of clusters), training set X(drop x0=1 addition)
* If no points assigned to one centroid, just eliminate it.
#### K-means for non-clear-separated clusters
 Some time you can get the separation well, sometimes not.

## Optimization Objective
* Ci: which cluster the ith X is assigned to
* mu(k): cluster centroid k
* mu(ci): cluster centroid of ci
* J= 1/m * sum(||xi-mu(ci)||^2), minimize J
* Tring to find parameter C and mu, to minize the cost function
* Cost function is also called the distortion of k-means algorithm
* Explanation:
  1. Assign points to the closest cluster centroid, which is minimizing J according to the centroids
  2. Reassign points to the centroids, which is minimizing J according to the points
  3. The J is always reducing.

## Random Initialization
* Initialize cluster centroids: 
 1. K < m
 2. Randomly pick K training examples
 3. Set K equal to these K examples
* Ramdon initialization will lead to different undesired local optima
* To address the local optima, run k-means many times and get the minimal J, which will lead to the global optima.
* If k=2 to 10, doing multiple times can find a good centroids.
* If k > 100, no much difference between the different trials.

## Choose the number of Clusters K
### Elbow Method
Draw the K - J graph, get a curve that decrease with the increase of K, select the elbow point(the point 
that curve stops decrease rapidly).  
But elbow method is not that clear in many situations, there is not a clear elbow in the graph.
### Make the cluster number serve the down-stream purpose
example: want to make five different size t-shirts, so cluster the data into five different clusters, k = 5.  

# Dimensionality Reduction
* Data compression: Reduce the redundent features into the same one, run faster, reduce space usage.
* Data Visualization: If we can understand the data better, we can design algorithms more effective.

## Princal Component Analysis
This algorithm is trying to minimize the projection error(the distance between the projecting surface and the acutal points).  
It is the same as finding a vector which makes the projecting distance the smallest.  
For 3d, find a pair of vectors.  
Reduce from nd to kd, find k vectos , if you want to reduce the dimensionality to k.  


PCA and Linear Regression are different:
 * they try to minimize different distance.  
 * There is no y in linear regression, no y trying to predict in PCA.


Data preprocessing for PCA:
 * replace xj with xj-mu
 * rescale the range of x, have xj / reasonable_value

Procedure:
 1. Covariance matrix sigma
 2. Compute eigenvectors, sigular value decomposition(奇异值分解), [U,S,V]=svd(Sigma)
 3. U is a nxn metrix, ui will be the exact vectors we want.
 4. [u1 u2 u3 ... uk] is nxk matrix, is the reduce matrix we want, zi = U' * Xi will produce k dimensional zi
 5. For all xi, compute U' * xi.
* Sigma = 1/m * (X' * X); X=[x1' x2' x3'...]
* Ureduce = U(:,1:k) --> nxk matrix
* z = Ureduce' * xi;

 
