# Supervised Learning

## Linear Regression

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
