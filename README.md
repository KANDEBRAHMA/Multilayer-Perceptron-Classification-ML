# Multilayer-Perceptron-Classification-ML
 Implemented MLP using neural networks in Python


In machine learning, the field of artificial neural networks is often just called neural networks or multilayer perceptrons.

* Fitting the Train Dataset:
    * Randomly initializing hidden weights in the shape of(length of features,number of neurons in hidden layer).
    * Randomly initializing output weights in the shape of(number of neurons in hidden layer, number of target classes).
    * Forward Propagation:
        * We calculate the dot product of features and hidden weights and pass them through the specified activation function and store them weights of hidden layer neurons.
        * Then, we calculate the dot product of hidden layer neurons with output weights and pass them through the specified activation and softmax the result and store them as weights of output layer neurons.
        * Once we get all the weights we call backpropogation function.
    
    * Backward Propagation:
        * Calculate error in output layer
        * Update all weight between hidden and output layer
        * Calculate error in hidden layer
        * Update all weight between hidden and output layer

    We will stop calling backpropagation once the error was minimum.

    So, after the forward and backward propagation on the datapoints in the train dataset we get the updated weights that we can use for predicting the target class for test data points.

* Predicting the Class for test data set:
    * Perform forward propagation with updated weights and the weights having maximum probability at the output layer will the target class for that datapoint.

* Different Activations functions used are:
    * Sigmoid 
    * Tanh
    * Identity 
    * Relu

    Reference is taken from https://cs230.stanford.edu/files/C1M3.pdf

    * One hot encoding:
        * Creating a numpy array with zeros of shape(size of dataset,unique target classes)
        * Then by iterating over targets we update numpy array with specified target column with one.