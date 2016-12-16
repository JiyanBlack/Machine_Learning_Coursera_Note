# Intro to nerual networks

* neurons are basically computational units that take inputs (dendrites) as electrical inputs (called "spikes") that are channeled to outputs (axons).

* inputs/dendrites are x1...xn, x0 is called "bias unit" and always equal to 1
* The same sigmoid(logistic) activation function.
* thetas are called weights (just another name).
* layer 1 is called "input layer"
* intermediate layers are called "hidden layers"
* the last layer must output something, so it's called "output layer"
* theta<sup>j</sup> is the matrix of weights that mapping from layer i to i+1
* If network has sj units in layer j and sj+1 units in layer j+1, then Θ(j) will be of dimension sj+1×(sj+1).

* We are actually doing the same thing as logistic regression at the output layer.
* bias unit (a0 = [1..1]) is added every layer to add constant bias.

# Multiclass Classification
The output layer will have several activations, each of then produce a vector that indicates the type of the output.
