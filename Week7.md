# Support Vector Machine
Change the Cost - Z from a log curve to a line vector. Similiar process, but give the computational advantage.  
Cost function is c * Cost + regularization_term , not Cost + lambda * regularization_term  
* if y=1, we want hx >=1(not just >=0), and cost =0;
* if y=0, we want hx <= -1(not just < 0), and then cost = 0;
* If C is large, the Cost term should be extremely small in order to make the total cost small. 
* Benefits: produce larger margin classifier, thus more reasonable when boundary is clear.
* Disadvantage: more sensitive to outlier, can be fixed by reduce the c value.

# Kernels
* Kernels are landmarks(selected data points)
* the x1,x2....xn is substituted by f1,f2,f3...., F vector is the distance of the original Xi to those landmarks
* f is the similarity between training examples and selected landmarks
* if xi is close to fi, then fi = 1; else 0;
* So thetai decide that, if one sample is close to xi, whether it is more likely to be negative or postive.
* Choosing the Landmarks:
  1. Given X, n training examples
  2. Choose the training examples as landmarks dataset.
  3. f1 = similarity(xi,x1), f2 = similarity(xi,x2) ... f(i) = [f0=1, f1, f2, f3...]
* C(1/lambda) is large: lower bias, higher variance
* C is small: higher bias, lower variance
* sigma: exp(-(||length||/bias)^2) is large: higer bias, because the similarity function become smooth
* simga is small: very abrupt curve, lower bias, higher variance

# Practical SVM
1. Use SVM package (e.g. liblinear, libsvm,...) to solve for parameters theta. 
  * Need to specify parameter C
  * Choice of kernel(similarity function)
    1. no kernel(linear kernel), large features, m small
    2. Gaussian kernel, small features, m large
    3. Perform feature scaling before using Gaussian kernel
  * All kernels must statisfy the "Mercer's Theorem", which enable the SVM to optimize, run efficiently and do not 
  diverge.
  * Polynomial Kernel: k(x,l) = (Xt * l + constant)^degree, usually performe worse than Gaussian kernel
  * String kernel, chi-square kernel, histogram intersection kernel... all used to produce the difference between
  landmarks and data...
2. Multi-class classification
  * Many SVM packages already have built-in multi-class classification functionality.
  * Otherwise, use one-vs-all method. (e.g. for hand writing recoginition, if y=5, set a vector that 5th is 1 and others 
  are zeor : [0,0,0,0,1,0,0...])
3. Logistic regression vs SVM
  * If n is large relatively to m, use logistic regression or SVM without kernels.
  * If n is small and m is intermediate: use SVM with Gaussian kernel
  * If n is small, m is very large: create/add more features, use logistic regression or SVM without a kernel, because 
  the Gaussian kernel is relatively slow..
4. Algorithm is important, but often the features selecting/data amount/parameter setting are also very important.
