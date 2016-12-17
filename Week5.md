# Neural Network and Backpropagation
* L = total number of layers in the network
* sl = number of units (not counting bias unit) in layer l
* K = number of output units/classes

## Binary classification
y = 0 or 1, 1 output unit, SL = 1, k(class number) =1

## Multi-class classification (K classes)
K output units, y=[k * (0 or 1)], this is one vs all method, that only one element in y is 1, others are all zero.

## Cost Function
Cost Function of neural network is basically a sum of the m training sets' sum of all k classes of each individual training set.

## Derivitives and back propagation
"Backpropagation" is neural-network terminology for minimizing our cost function   
general idea: 

* use forward propagation to get all activations.
* calculate the difference of predictions and the value it should be for every layers.
* use the difference to get the partial derivitives of each layer's theta.

Steps:  

1. Set a(1) = X;

2. Perform forward propagation to compute all a(l) for l=2:L;

3. Comput delta(L) = a(L) - y (the difference between the prediction and actual data);

4. Perform backward propagation to compute delta(L-1,L-2....2);

5. △(l) = △(l) + a(l) * delta(l+1)

6. Derivations: D(l) = 1/m * △(l) + lambda / theta(l) if j != 0 

# Backpropagation in Practice

## Advanced optimization
* Problem: function [jval,gradient] = costFunction(theta); optTheta = fminuc((t)(@costFunction(,,,)),initialTheta, options)  --> assume the theta/gradient are all vectors;
* Neural Network: [theta1,theta2,theta3...] , gradient: [gradient1....], are all matrix, so not suitable for advanced optimization algorithm, thus need to be transformed in order to fit into optimization function.
* Transform: thetas= [theta1(:) ; theta2(:)...], DVec = [D1(:); D2(:); D3(:)...];
* Turn back into matrix: theta1 = reshape(thetas(1:110),10,11);
* Steps: 
  1. unroll all initial thetas to get a vector of initialTheta
  2. pass to the optimize function
  3. inside cost/gradient calculation function, reshape the theta-vector, do calculations.
  4. unrol gradients into a vector and return this vector.
