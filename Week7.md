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
