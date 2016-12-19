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
Question is: d = degree of polynomial is the best. We can fit d, to make the trained theta with test sets better fitting.  
We cannot use training set/test set model to get the best performance. Because we get the parameters from the test set and it is not fair to evaluate use the test set again.  
Solution: Splitting into three pieces: Training set(60%), Cross Validation Set(CV,20%), Test set(20%).  

Steps:
1. Train the model using training set with different polynomials.
2. Test the models on the cross validation sets, get a best parameters that has the lowest cross-validation error.
3. Test the result model with the test.

# Diagnosing bias vs variance
Bias --> underfitting, Variance --> overfitting.  
* Plot degree of polynomial to the training and cross-validation error graph.
* Overfitting(variance): J(training) low and Jcv hight. Jtraining - Jcv is high.
* Underfitting(bias): Jtrain is high and Jcv is high, Jtrain ~= Jcv.

