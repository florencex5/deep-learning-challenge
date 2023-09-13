# Neural Network Report


## Overview
* The main purpose is to create a model that can help nonprofit foundation Alphabet Soup to select the applicants for funding with the best chance of success in their ventures. 
* Use the features in the provided dataset to create a binary classifier that can predict whether applicants will be successful if funded by Alphabet Soup


## Data Preprocessing
* Exclude the identification columns (i.e. "EIN" and "NAME") which do not contribute to modeling process
* Count the each unique value in column "APPLICATION_TYPE" and aggregate values with a frequency count under 500 into a new category labeled "Other" within the same column.
* Count the each unique value in column "CLASSIFICATION" and aggregate values with a frequency count under 1800 into a new category labeled "Other" within the same column.
* Convert the categorical data ('APPLICATION_TYPE', 'AFFILIATION', 'CLASSIFICATION', 'USE_CASE',
       'ORGANIZATION','INCOME_AMT', 'SPECIAL_CONSIDERATIONS') to numeric format using `pd.get_dummies()`
* Set the column "IS_SUCCESSFUL" as **target variable** for for model testing,training and evaluation
* Include the rest of the transformed categorical data and numeric data as **features** for model testing, training and evaluation
* Apply the standard scaling method to normalize the values within the feature columns to ensure the consistency of data


## Model Training
* When splitting the data for training and testing, the default test data size of 0.25 was used. This means that 25% of the dataset was reserved for testing, while the remaining 75% was used for model training and evaluation.


## Model Evaluation
* **Hyperparameter Tuning and Model Selection:**
    * Employed a hyperband tuner to optimize hyperparameters. Based on the hyperparameter tuning results, the first attempt deep learning model achieved the highest accuracy score of 73.15%.
    
* **Model Improvement Attempts:**
    * In pursuit of enhanced model performance by adjusting the number of neurons and hidden layers.
        * In the second attempt, the number of neurons in the first layer increased from 12 to 15, while the second layer expanded from 12 to 29 neurons, keeping all other parameters identical to the first attempt.
        * In the third attempt, an extra hidden layer was introduced, resulting in a total of three hidden layers.The third hidden layer consisted of 13 neurons with "Tanh" activation function.
        
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

* Therefor, in light of the model's performance, I recommend using other activation functions (e.g. Softplus,Elu). As the choice of activation function plays a crucial role in shaping the model's learning capacity. Additionally, the incorporation of ensemble methods, such as Random Forest or Gradient Boosting, could be explored to improve overall predictive performance. 
