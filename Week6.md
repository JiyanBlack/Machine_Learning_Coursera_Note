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

# Learning Curve
Plot Jtrain or Jcv as a function of m(training set size). Reduce the training set size.  
* High Bias: If Jcv reduces fast/ Jtrain increase fast, they both end up very high and flaten very quickly, means the model has high bias(underfitting), that is feeding more data can not really improve the performance.
* High Variance: Jtrain is always low, but Jcv is relatively high and Jcv - Jtrain is high as well. Getting more data is likely to help.

# Decisions to take
1. Getting more training examples --> fix high variance.
2. Trying a smaller sets of features --> fix high variance.
3. Trying a biger data set --> fix high bias.
4. Add polynomial features --> fix high bias.
5. Increase lambda --> fix high variance.
6. Decrease lambda --> fix high bias.
7. Small/Simple neural network --> underfitting --> cheap computation, less effective
8. Large neural network --> prone to overfitting --> expansive computation, more effective. 

Usually we use large neural network with regularization to fix overfitting. Using training/cross-validation dataset to evaluate 
degree(polynomial), neural network layers, regularization parameter(lambda). Use the test dataset to evaluate the trained parameters.

# Build a Spam Classifier
* Choose n words to be features, indicate of spam/non-spam;
* Xj = 0 if word j not in email else 1;
* Pick most frequently appear words in email.
* How to make the classifier accurate:
   1. Collect lots of data
   2. Develop sophisticated features on email routing information(from email hearder)
   3. Collapse the similar features: "discount" and "discounts"
   4. Develop algorithm to detect delibrate misspellings (m0rgage,med1cine)
   5. ......

# Error Analysis
Recommend Approach:  

1. Start with a simple algorithm, implement and test it on the cross-validation data.
2. Plot learning curve, decide the problem is the underfitting(high bias) or overfitting(high variance) problem.
3. Error Analysis: manually examine the wrong predictions that your algorithm made on. Spot systematic pattern of those errors. New features can come out from it.

# Skewed Class and Error Metric
* Example: 1% error on test sets. But only 0.5% people actually got cancer....
* Data is skewed, the negative/postive is way more than the other.
* Precision/Recall method
   1. precision: Of all predictions that y=1, what fraction that y is acutally 1;
   2. Recall: of all y is actually 1, what proportion that we predict y=1;
 * Precision: true postives/(true positives + false postives), is the precision of our predictions
 * Recall: true postives / actual postives, is the effectiveness of our predictions 
* Precision and recall are usually contradictory and a tradeoff needs to be made.
* Reduct the two into one metric, F Score = 2* (PR)/(P + R) is better than mean value.
