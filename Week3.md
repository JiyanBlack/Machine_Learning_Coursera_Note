# Classification

* Email: Spam/Not Spam, Tumor: Malignant/ Benign
* Apply linear regression to classification is a bad idea. Because outliers can greatly change the predictions.
## Logistic Regression Algorithm

### Hypothesis Representation
* hypothesis=g(theta * x) 
* Sigmoid/Logistic function g(z) = 1/(1+e^(-z))  
* h(x) = P(y=1 at x;theta) --> the estimated probability that y=1 on input x

### Decision Boundary
* Suppose y=1 when h >=0.5, if h < 0.5 then y=0 
* when y=1, h>=0.5, theta<sup>T</sup> * x >= 0  
* Example:  
   h(x)=g(-3+x1+x2)    
   -3+x1+x2>=0 --> y=1  
   -3+x1+x2 < 0 --> y=0  
   line: x1+x2=3 is a decision boundary
### Cost Function 
* Cost(h(x),y) = 1/2 * (h(x)-y)^2 for linear regression, become non-convex for logistic regression
* Cost(h(x),y) = -log(hx) if y=1, -log(1-hx) if y=0
* Cost = -ylog(hx) - (1-y)log(1-hx) --> more compact and easier to implement
* J(0) = -1/m  * (sum(i=1 to m) for J0(xi))

### Advanced Optimiatoin
* Cost function J(0), we want to minimize J(0), Given 0, we want to code to compute: J(0) and partial derivitive of J(0) to 0j
* With J(0) and partial derivitive of J(0) to 0j, there are many other algorithms to optimize Cost function:  
  Conjugate Gradient  
  BFGS  
  L-BFGS  
  Advantages:  
  * No need to manually pick alpha
  * Often faster than gradient descent  
  Disadvantages:  
  * More complex
* How to use these functions in Matlab:
 * set a function return [J,gradient], J calculates the cost value, gradient calcultes the partial derivitives
 * Set initial thetas 
 [optTheta, functionVal, exitFlag] = fminunc(@costFunction,initialTheta,options)
