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
