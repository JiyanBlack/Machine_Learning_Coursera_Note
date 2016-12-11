# Supervised Learning

## Gradient Descent for Linear Regression

### Multiple Features (Multivariate Linear Regression)

Multiple features, aim to reduce to a single prediceted result.  
h = θ0 * x0 + θ1 * x1 +..... θn * xn  
x0=1 and θ0 is the constant factor  
So θ<sup>T</sup> * x = the final predicted result

### Gradient Descent for multiple features
Basically same as gradient descent for two features

repeat until convergence:{  
θj:=θj−α1m∑i=1m(hθ(x(i))−y(i))⋅x(i)j  
for j := 0...n
}

### Feature Scaling
Idea: make sure features are on a similar sacle.  
Normally, get every feature into approximately -1 <= xi <=1 range.
Dont worry if its -2~2 or 0.1 ~ 0.5  
but it cannot be -100 or 0.001

### Mean Normalization
Replace xi with xi- meani to make features have approximately zero mean.(Do not apply to x0=1)

### Combined:
xi := xi - mean i / std or (max-min)

The normalization makes the gradient descent process a lot faster.  
We can speed up gradient descent by having each of our input values in roughly the same range. This is because θ will descend quickly on small ranges and slowly on large ranges, and so will oscillate inefficiently down to the optimum when the variables are very uneven.   
Two techniques to help with this are feature scaling and mean normalization. 

### Learning rage alpha -- a
Plot No.of Iteratinos -- J(theta), it should decreases and indicate that your algorithm is working. If the curve is close to flatten  
then it can be assumed to be achieved the goal.   
If J is increasing, a should be smaller to converge.  
If a is too small, the converging process can be very slow.  
### Automatical convergence test:
 test if the J decreases less than a value during each iterration (better to look the plotting)

### Polynomial Regression

Our hypothesis function need not be linear (a straight line) if that does not fit the data well.

We can change the behavior or curve of our hypothesis function by making it a quadratic, cubic or square root function (or any other form).

One important thing to keep in mind is, if you choose your features this way then feature scaling becomes very important.

## Normal Equation -- Linear Regression
Method to solve for theta analytically.  
Get every partial diriatives for theta j = 0, and calculate the value of theta j.  

θ=(X<sup>T</sup>X)<sub>−1</sub>X<sup>T</sup>y   
x=[    
x10 x11 x12 x13  
x20 x21 x22 x23  
]  
y=[  
y1  
y2  
]

* No need to do feature scaling for normal equation.  
* Normal Equation is more convenient. But calculate the inverse of X<sup>T</sup>X is actually O(n3).   
* For large dataset, should use gradient descent (usually when normal equation is too slow)

### None-invertible X<sup>T</sup>X
* Pretty rare  
* pinv (psudo invert) will still get the true value even if it's invertible  
* Reasons may be: 1. Redundant features; 2. Too many features, or too few training sets. We can use regularization to solve this problem.  

