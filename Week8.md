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

## Principal Component Analysis
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

## Reconstruct from Compressed Matrix
 * z = U' * x, xapprox = U * z, xapprox is very close to the original graph.
 * Reconstruct graph looks like that points are moved to the same projected surface.
 
## Choosing the number of pricipal components - k
* Average squared projection error: 1/m * sum(||xi-xapprox||^2)
* Total variation in the data: 1/m * sum(||xi||^2)
* Choose k to be the smallest value that : aspe/tv <= 0.01, make 99% of variance is retained
* Goal is to reduce as much dimensions as possible but retain more information
* Steps:
 1. Try PCA k=1;
 2. Compute Z and retain ratio
 3. Check if ratio < 0.01(or any other reasonable value)
 4. Increase the k value.
* In [U S V], the S is a diagonal matrix, the same retain ratio can be computed using S more efficiently

## Supervised Learning Speedup with PCA
* With very high dimensional features, the learning algorithm is normally slow.
* Steps:
 1. Get unlabeled dataset: [x1,x2, ... xn]
 2. Generating reduced data set [z1,z2 ... zn]
 3. new training example [z1,y1] ... [zn,yn]
 4. learn hypothesis from the new training examples
* The reduce matrix U should only be obtained by running training dataset, not cv or test data.
* To get the predictions, cv and test data will also be converted by the same U produced by training dataset.
* Reduce matrix is just like feature scaling.
### Application of PAC:
* Compression --> save space , increase speed
* Visualization
* Bad use of PCA: 
  1. prevent overfitting, it works, but by throwing away information.
  2. When design ML system, do it without implement PCA, run once, if that is not your want(too slow, memory usage large), try PCA then.
