# Debug Learning Algorithms

* Get more training examples (but not always the more the better)
* Try smaller sets of features or additional features
* Try add polynomial features
* Decreasing/increasing lambda  

These are all big projects. The decision should be according to reasonable investigations. Rule out as many possibilities as possible.

* Machine Learning Diagnostic:
A test that you can run to gain insight what is/not working with the learning algorithm, give you a guidance of how to improve your algorithm.

# Evaluate Hypothesis
* Split the data into two potions, the first part is going to be the training set(70%), others(30%) to be test set.
* If it is overfitting, J(training) is low but J(test) is high.
* Usual steps:
    * Learn parameters from training data;
    * Compute the test set error J(test)
    * For classification error, except J method, there is a misclassification error. Error(h,y) = 1 or 0 (binary value)

# Model Selection Algorithm
The trained parameters always have lower error on training example data. So the overfitting problem is that the difference between the trained and unknown data is too big.   
Question is: d = degree of polynomial is the best.  
We cannot use training set/test set model to get the best performance. Because we get the parameters from the test set and it is not fair to evaluate use the test set again.
