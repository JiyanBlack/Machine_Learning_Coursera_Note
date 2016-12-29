# Anomaly Detection
## Introduction
* We have a set of data that is all normal examples.
* So we would like to know whether a new datum is normal or not.
* To achieve this, we need to build a model, P(xtest) < threshold --> anomaly
* Examples: 
    1. Fraud detection --> detect whether a user is unusual or not.
    2. Manuafacturing
    3. Monitoring computers in a data center, to watch out the performance of a machine

## Normal Distribution(Gaussian Distribution)
X ~ N(mu,sigma^2)

## Density Estimation
p(x) = prod(p(normal xj)), if p(x) < threshold, then it's anomaly.  

## Evaluate the Estimation System
* We have some labeled data that are known normal or anomalous
* We have the training set are unlabeled and normal examples.
* Cross-validation set, are known to be normal and anomalous. 
* Test set, are known examples.
* Example: 10000 good engines, 20 flawed ones.
    1. Training set: 6000 good ones as training set.
    2. Cross-validation set: 2000 good ones, 10 anomalous.
    3. Test: 2000 good, 10 anomalous.
* Steps:
    1. Fit model using normal distribution to the training set.
    2. Select features and threshold value on the cv sets.
    3. On a cross-validation/test example x, predict y =1(anomalous) or 0(normal)
    4. Estimate the model on true/false positive/negative, recall/precision and F1 score
    
## Supervised Learning Algorithm and Anomaly Detection Algorithm
* Why we do not just use supervised learning instead of nomaly detection:
    1. Anomaly detection: a very small number of postive examples and large number of negative examples.
    2. Many different "types" of anomalies, hard for any algorithm to learn from postive examples the features of normal
     examples.

## Choose what features you use
1. Non-Gaussian Model(Asymetric)
    * Take a log transformation(X becomes log(X), or X^0.5) to the data, the whole graph will look like Gaussian distribution
2. Error analysis for anomaly detection
    * P(x) is similar for normal and anomalous examples.
    * Solution: look at the false error, find a new feature to detect this anomaly.
    * With this new feature, it would be easier to detect the features.
3. Experience:
    * Choose the feature that is very large or small when it's in anomalous status.
    
# Multivariate Gaussian Distribution
* Problem is that the probability graph is a circle, so cannot fit in many other shapes normal/anomalous model
* Multivariate Gaussian Model:
    1. Parameters: mu --> n vector, sigma --> nxn matrix
    2. mu determine the center of the model
    3. sigma determine the shape and correlation of Xn
* Steps:
    1. Fitting model: mu = mean(sum(X)), sigma = 1/m * (X * X');
    2. Given a new example, compute: p(x)
    3. compare p(x) to threshold
* Normal Gaussian model is a special case of multivariate Gaussian model.
## When to use which model?
* Original model: 
    * If x1 and x2 have some kind of relationship, create a new feature x1/x2.
    * Computationally cheaper, so scales better to large n
    * Works fine even training set is small
* Multivariate Gaussian: 
    * Automatically captures the correlations.
    * Computaionally expensive for invert matrix
    * must have m>n and no redundant feature, otherwise sigma is non-invertible
    
# Recommender System
## Content-based Recommender Systems
* Each user has a theta vector that defines the liking and dislikings of this user. 
* Predictions are produced by theta' * x (the content attribute vector)
* Essentially like linear regression, learn theta from the movies that the user has rated.
* Minimize J(theta1,2,3...n)

## Collaborative Filtering
* Learn features from theta and current data, then learn theta from features, back and forth, improve the performance
 of this algorithm.
* Every user behaviour will help to improve the algorithm and user's own recommendations, so it is called collaborative
## Collaborative Filtering Algorithm
* The intuitive way to improve
    1. Given x1, x2, x3 .... estimate theta1, theta2, theta3...(known movie type, predict user mark)
    2. Given theta1, theta2, theta3 ... estimate x1, x2, x3 .... (known user preference, predict movie type)
* The combined way: add the two cost function together to minimize both at one time.
* No need to set x0=1 or theta0 = 1. Because we are learn theta and x simutaneously, no need to hard code some 
features equal to one, if the algorithm needs 1, it can learn by itself.
* Steps:
    1. Initialize x1....xn, theta1,... thetan to small random values
    2. Minimize J(xs,thetas) using gradient descent.
    3. For a user with learned parameters theta,a movie with learned features x, predict a rating as theta' * x.

## Low Rank Matrix Factorization(another name) to find related entities
* It is hard to know what are the learned features.
* But movies with similar features will be liked.
* How to find movie j related to movie i?
    * || xi - xj || is small --> similar
 
## Recommender Systems Mean Normalization
* calculate mean of Y
* have Y - mean, get the sum = 0 for each row in Y
* For user j, on movie i, predict thetaj' * xi + meani
* It's the same as predict the new user the average rating.
