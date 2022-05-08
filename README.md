# Neural-Networks-for-Applications
## Overview:
### Background:
Alphabet Soup's business team supplied a csv file with data on 34000 organizations seeking funding. They have tasked us with creating a Neural Network to determine what organizations should be given funding.
### Purpose:
We are creating a Nueral Network trained on the dataet provided to predict whether or not an org would recieve funding. First we must prepare the data and make it work for us. From bucketing to encoding to scaling, vaguely in that order. The prepared data is then split and used to train the model to be tested with the test set. Then attempt to achieve a target accuracy level of 75% on the testing set. In order to do so, we will try to make a gridsearch-like loop to test all possible 
## Results:
### Data Preprocessing:
- I considered the IS_SUCCESSFUL to be the target variable since its the result of the orgs campaign.
- I dropped the identifying columns since it has nothing to do with analysis, in the optimization attempts I drop ask amount and any variable with very low correlation.

The following were dropped as a result of the low correlation (after being encoded):

![image](https://user-images.githubusercontent.com/71575748/167300766-32339027-cdea-4bfd-b22a-7302f7a717a2.png)

- Everything else was kept as a feature.
### Compiling, Training, and Evaluating:
In Referrence to the optimization attempts:
- The first model is described as follows:
  - input layer with 90 neurons, relu activation function
  - first hidden layer with 70 neurons, tanh activation function
  - second hidden layer with 70 neurons, relu activation function
  - output layer with 1 neuron, sigmoid activation function
  - Trained over 10 epochs to achieve maximum testing accuracy
  - 73.64% accuracy on testing set.
- The second model is desctibed as follows:
  - input layer with 100 neurons with relu activation function
  - first hidden layer with 80 neurons, tanh activation function
  - second hidden layer with 60 neurons, relu activation function
  - third hidden layer with 80 neurons, tanh activation function
  - output layer with 1 neuron, sigmoid activation function
  - trained over 100 epochs
  - 73.68% accuracy on testing set.
- The third model is described as follows:
  - input layer with 100 neurons with tanh activation function
  - first hidden layer with 70 neurons, tanh activation function
  - second layer with 70 neurons, tanh activation function
  - third layer with 60 neurons, tanh activation function
  - fourth layer with 70 neurons, tanh activation function 
  - output layer with 1 neuron, sigmoid activation function
  - trained over 120 epochs
  - 73.77% accuracy on testing set.
- unfortunately none were able to achieve target performance. With more time I'm sure with a wider and tighter net of parameters, I think a model would eventually be made that will achieve the target accuracy.
- I dropped a bunch of variables I saw a irrelevant. I made a group of nested loops running through lists of parameter inputs to run possible combinations. Such as input and hidden neurons, input and hidden activation functions etc. then the best of those was looped through a list of epoch list. A lof of for loops were used and nested in eachother. The best model was saved to a class for storage and a function was made to display the specs of the model and its accuracy on the testing set.
## Summary:
I was unable to meet the 75% accuracy threshold, perhaps with more time to run through a bigger and tighter net of inputs there could be a model that does succeed. Alternatively a tuned random forrest classifier model could be used as an alternative. Or a hyperparameter tuned XGBoost classifier model could be used as a alternative. This is because both of the Random forest classifier works very similarly to a neural net model. The XGBoost model is one I've seen work to great success, and with proper tuning using gridsearch to tune the hyperparametersm it could be one to compete with the Neural net. It could possibly outperform the models I came up with for this project.
