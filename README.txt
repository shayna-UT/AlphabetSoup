1. How many neurons and layers did you select for your neural network model? 
    - Number of input features: 405
    - Number of Neurons in hidden layer 1: 100
    - Number of Neurons in hidden layer 2: 30
   
   Why?
    - This is a relatively large dataset of 34,299 rows and 405 columns. A deep learning model was chosen 
      to allow the model to train on more parameters, and thus have more opportunities to find trends in the dataset.
    - In addition to having enough parameters ("opportunities") to train the model, it is important to also not over-fit the model.
      It important to not exceed the total number of data points in the training dataset.
    - Based on the above inputs, the model had 43,661 total params to train the model on. The first layer has 405 input values (length of 
      training dataset) multiplied by the 100 neurons plus 100 bias terms for each neuron. This gives us a total of 40,600 weight parameters.
      Since this is a deep neural network, the outputs of one hidden layer of neurons (that have been evaluated and transformed 
      using an activation function) become the inputs to additional hidden layers of neurons. Therefore, the 100 neurons from 
      the first layer are passed into the second layer and multiplied by the number of neurons in the second hidden layer. Then a bias 
      term for each of the number of neurons in the second hidden layer are added to the number of parameters in the second hidden layer. 
      This resutls in an additional 3,030 parameters ( (30 neurons x 100 outputs from hidden layer 1) + 30 bias terms ). Since this is a 
      classification model (yes/ no binary decision), only one output neuron is needed. Therefore, the 30 neurons from the second hidden
      layer is passed to the one output neuron, resulting in an additional 31 parameters ( (1 output neuron x 30 outputs from hidden layer 2) 
      + 1 bias term). 

2. Were you able to achieve the target model performance? 
    - Yes; the target model performance was 75%, and about 79% accuracy was achieved. 
   
   What steps did you take to try and increase model performance?
    - Originally, the "NAME" column in the dataframe was dropped and the model was trained without it. Adding the "NAME" column back into the 
      training dataset significantly increased the performance of the original model by about 5%, demonstrating that it is an important feature. 
    
    - Multiple modifications were made to the original model in an attempt to see if the performance of the model would be significantly changed.
      In general, the model remained at an accuracy score of about 78%, demonstrating there may be a limit to the model performance. 

3. If you were to implement a different model to solve this classification problem, which would you choose? 
    - Random Forest 

   Why?
    - Random Forest models are very similar in structure to neural networks. Random forest models use a number of weak learner algorithms 
      (decision trees) and combine their output to make a final classification (or regression) decision. Therefore, a random forest model 
      with a sufficient number of estimators and tree depth should be able to perform at a similar capacity to most deep learning models.
      One drawback of Random Forest models is that it can only handle tabular data, while neural networks can handle more complex data such 
      as images abd natural language. Also, neural networks are good at identifying variability since input data is evaluated within in a 
      single neuron, as well as across multiple neurons and layers. 
    - A Random Forest model was selected since we are inputting tabular data and Random Forest models are capable of handling outliers and 
      non-linear data. The model was tested with 128 estimators and was able to achieve very similar accuracy to the neural network. It is 
      important to note that the Random Forest model run time was quicker compared to the neural network.  