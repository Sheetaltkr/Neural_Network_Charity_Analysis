# Neural_Network_Charity_Analysis

## Background
Alphabet Soup is a philanthropic foundation dedicated to helping organizations that protect the environment, improve people’s well-being and unify the world. The foundation has raised and donated over $10B in the past 20 years to be invested in lifesaving technologies and organizing re-forestation groups around the world. 

Beck’s is a data scientist and programmer who is in charge of data collection and analysis for the entire organization. Her job is to analyze the impact of each donation and vet potential recipients. This helps ensures that the foundations money is being used effectively.
In some cases, the organizations are fraud, hence it is extremely important to predict which organizations are worth donating to and which are too high risk.

## Purpose:
- Help Beck’s and Alphabet Soup determine which organizations should receive donations.
- Design and train a deep learning neural network model using Python Tensor flow library. This model will evaluate all types of input data and produce a clear decision-making result.
- Create a binary classifier that is capable of predicting whether applicants will be successful if funded by Alphabet Soup using the features in the provided dataset charity_data.csv received from Alphabet Soup’s business team.

##  Results:

### Data Preprocessing
1. What variable(s) are considered the target(s) for your model?
   One variable listed below is considered the target for the model
  - IS_SUCCESSFUL
   
2. What variable(s) are considered to be the features for your model?
  The variables listed below are considered to be the features

  - APPLICATION_TYPE          
  - AFFILIATION                 
  - CLASSIFICATION            
  - USE_CASE                    
  - ORGANIZATION                
  - STATUS                       
  - INCOME_AMT                   
  - SPECIAL_CONSIDERATIONS       
  - ASK_AMT                   

3. What variable(s) are neither targets nor features, and should be removed from the input data?
  - EIN
  - NAME
  
  
### Compiling, Training, and Evaluating the Model
1. How many neurons, layers, and activation functions did you select for your neural network model, and why?
There is one input layer , two hidden layers and an output layer
The count of neurons for first hidden layer is **80** and in second **30** as no. of input variables is 9 hence the hidden layer neurons need to be atleast 2-3 times of input variables. The hidden layer activation function used is "ReLU" for both layers as the ReLU function is ideal for looking at positive nonlinear input data for classification. 
2. Were you able to achieve the target model performance?
   No, the maximum accuracy achieved was ~71%
3. What steps did you take to try and increase model performance?

**Trial1**: AlphabetSoupCharity_Optimization.ipynb

In this model, the neurons in second hidden layer have been reduced to 28. The accuracy improves to ~64% and loss changes to 0.64
-  number_input_features = 43
-  hidden_nodes_layer1 = 80 activation = relu
-  hidden_nodes_layer2 = 28 activation = relu
-  output activation = sigmoid
-  epoch = 50
-  
**Trial2**: AlphabetSoupCharity_Optimization_1.ipynb

In this model, the neurons in first and second hidden layer have been increased to 120 and 60. The accuracy improves to ~69% and loss changes to 0.72
-  number_input_features = 43
-  hidden_nodes_layer1 = 120 activation = relu
-  hidden_nodes_layer2 = 60 activation = relu
-  output activation = sigmoid
-  epoch = 50

**Trial3**: AlphabetSoupCharity_Optimization_2.ipynb

In this model, the neurons in first and second hidden layer have been reduced to 80 and 28 and column USE_CASE has been dropped to check if this is a noisy feature. The accuracy improves to ~71% and loss changes to 1.31 which is not ideal. 
-  Additional feature dropped = USE_CASE
-  number_input_features = 43
-  hidden_nodes_layer1 = 80 activation = relu
-  hidden_nodes_layer2 = 28 activation = relu
-  output activation = sigmoid
-  epoch = 50


**Trial4**: AlphabetSoupCharity_Optimization_3.ipynb

In this model, third hidden layer has been added with neuron count as 10 and the neuron count in first 2 layers is increased to 160 and 40 respectively. The accuracy degrades to ~59% and loss changes to 0.65. 

-  number_input_features = 43
-  hidden_nodes_layer1 = 160 activation = relu
-  hidden_nodes_layer2 = 40 activation = relu
-  hidden_nodes_layer3 = 10 activation = relu
-  output activation = sigmoid
-  epoch = 50

## Summary:
Summarize the overall results of the deep learning model. Include a recommendation for how a different model could solve this classification problem, and explain your recommendation.

-  The maximum accuracy with lower loss we see is **69%** with loss of** 0.72**, by increasing the number of neurons from the original model. Various attempts have been made by tweaking the no of neurons, hidden layers, changing activation function and dropping a couple of columns. However there was no improvement in model accuracy.
-  One can re-try using more data to train the model.

### Recommendation:
- We can try with just 1 input layer and 1 output layer with 0 hidden layers using just Sigmoid activitation function. 
- Sample values could be generated to train the model better.

