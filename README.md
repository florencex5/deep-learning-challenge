# Deep Learning Model (Neural Network)

## Overview
* The main purpose is to create a model that can help nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures. 
* Use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup

## Model Evaluation
* **Model Performance Results:**
* 1st attempt (Epochs = 100)
    * First hidden layer: 12 neurons / activation functions: Relu
    * Second hidden layer: 12 neurons / activation functions: Relu
    * Output layer: 1 neuron / activation functions: Sigmoid
    * Model Accuracy: 73.15%
    
* 2nd attempt (Epochs = 100)
    * First hidden layer: 15 neurons / activation functions: Relu
    * Second hidden layer: 29 neurons / activation functions: Relu
    * Output layer: 1 neuron / activation functions: Sigmoid
    * Model Accuracy: 72.66%

* 3rd attempt (Epochs = 100)
    * First hidden layer: 12 neurons / activation functions: Relu
    * Second hidden layer: 12 neurons / activation functions: Relu
    * Third hidden layer: 13 neurons / activation functions: Tanh
    * Output layer: 1 neuron / activation functions: Sigmoid
    * Model Accuracy: 72.87%

## Summary & Recommendation
* The most optimal deep learning model among the all three attempts is the first one, comprising two hidden layers with 12 neurons each employing ReLU (the Rectified Linear Unit) activation function, and a single neuron output layer with the sigmoid activation function. Unfortunately, this model was not able to achieve the desired 75% accuracy target. Based on two previous extra attempts, it is evident that increasing the number of neurons and layers, did not yield substantial improvements in accuracy. Although continuing to increase the number of neurons or layers can potentially improve the performance, but it also raises the risk of overfitting. 

* Therefore, in light of the model's performance, I recommend using other activation functions (e.g. Softplus,Elu). As the choice of activation function plays a crucial role in shaping the model's learning capacity. Additionally, the incorporation of ensemble methods, such as Random Forest or Gradient Boosting, could be explored to improve overall predictive performance. 
