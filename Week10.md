# Gradient Descent with Massive Data
* Best performance always comes from best data.
* The reason that machine learning is now popular is because nowadays large datasets are available everywhere.

## Stochastic Gradient Descent
* Gradient Descent(Batch Gradient Descent) is too computationally expensive
* Stochastic Gradient Descent is scaled for large data set.
* Steps:
  1. Randomly shuffle dataset.
  2. Repeat for i = 1...m, updata Thetaj = Thetaj - a * (hx-y)*xj
* Core of Stochastic: Start to update theta after looking at each example, not updating theta once after going 
through all data. Begin to descent after each iteration instead of after iterating all data.
* This algorithm wanders around the global minimum, unlike batch gradient descent always getting the exact minimum point. But result is pretty close to the global minimum and it is enough.
* The whole process may take 1-10 loops.

## Mini-batch gradient descent
* Between batch gradient descent and stochastic, batch size is 1~m
* Maybe faster than stochastic gradient descent only if you have good vectorization of mini-batch algorithm
* Mini-batch gradient descent is the common case, when b=1, its stochastic gradient descent, b=m it is batch gradient descent

## Debug and tune the gradient descent
* For batch, Plot Jtrain as a function of iterations, it should be decreasing
* For Stochastic, every 1000 iterations, plot average J for the last 1000 times.
* If it is too noisy, increase 1000 iterations. But will lose precision.
* TO help Stochastic gradient descent get a better performance, decrease alpha in each iteration.

# Online Learning
Learn from continuous stream of data.  
* Repeat forever:
  * Get (x,y) corresponding to a single user
  * Update theta using (x,y)
  * Discard the (x,y)
* It can adapt to change user preference.
* CTR: click through rate, learn P(click) 
  
# Map-Reduce
* Split the training set into machine-number portions
* Compute part of the final sumation in each machine
* take the temp parts and put them together
* update theta according to combined J

* If the learning algorithm can be expressed as computing sums of functions over the training set, map-reduce can be 
useful.
* It may also be useful for the multiple-core cpu.
