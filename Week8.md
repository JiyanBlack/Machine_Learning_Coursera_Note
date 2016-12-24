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
But elbow method is not that clear in many situations
