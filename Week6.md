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
