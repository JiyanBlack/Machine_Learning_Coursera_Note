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
  4. unroll gradients into a vector and return this vector.

## Gradient Checking
* Implement gradient checking for each complex algorithm is gradient checking
* get a partial derivitives of approximation of Derivitive-vector, and compare the gradients and approximate gradients
* Detail Steps:
  1. Implement backpropagation to compute Derivitive-Vector
  2. Implement numerical gradient approximations
  3. Make sure that they give similar values
  4. Turn off gradient checking, Using backprop code for learning. Because gradient checking is extemely expensive algorithm.

```matlab
epsilon = 1e-4;
for i = 1:n,
  thetaPlus = theta;
  thetaPlus(i) += epsilon;
  thetaMinus = theta;
  thetaMinus(i) -= epsilon;
  gradApprox(i) = (J(thetaPlus) - J(thetaMinus))/(2*epsilon)
end;
```
Once you have verified once that your backpropagation algorithm is correct, you don't need to compute gradApprox again. The code to compute gradApprox can be very slow.

## Ramdon Initialization
* Initialize to zero does not work well. Because all thetas are zero, so a11 = a12 , a21 = a22....will all be the same even after many iterations.
* So we random initialize the thetas, each element is between [-elp,elp]
```matlab
Theta1 = rand(10,11) * (2 * elp) - elp;
Theta2 = ...
```

## Summary of Implementation
1. Randomly initialize the theta value close to zero;
2. Implement forward/back propagation;
3. Do gradient checking;
4. Minimize cost function by gradient decent or other algorithms.

# Put It Together
1. Pick a network architecture; (3-5-4, 3-5-5-4, 3-8-8-4)
  * Input units and output units are fixed by problem and datasets;
  * Number of hidden layers: 
    * default is 1 hidden layer(most common)
    * for multiple hidden layers, have same number of hidden units in every layer. The more hidden units, usually the better.
2. Training a neural network
	1. Randomly initialize weights
	2. Implement forward propagation to get  h(x) for any x(i)
	3. Implement code to compute cost function J(theta)
	4. Implement back propagation to compute partial derivatives
	5. Use gradient checking to check for once
	6. Disable the gradient checking code.
	7. Use gradient decent or advanced optimization method with backpropagation to compute partial derivatives to  get parameters -- theta.
	8. J(theta) or neural networks is not convex, it can be contract to the local minimum. But usually get a very good optimization for theta.
