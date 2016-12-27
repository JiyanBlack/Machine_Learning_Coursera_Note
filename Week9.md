# Density Estimation
## Anomaly Detection
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
    
# Supervised Learning Algorithm and Anomaly Detection Algorithm
* Why we do not just use supervised learning instead of nomaly detection:
    1. Anomaly detection: a very small number of postive examples and large number of negative examples.
    2. Many different "types" of anomalies, hard for any algorithm to learn from postive examples the features of normal
     examples.
