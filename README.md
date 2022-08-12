# Neural_Network_Charity_Analysis
Learning Neural Network
## Overview of the analysis: 
The purpose of this assignment is to use deep-learning neural networks algorithms with TensorFlow in Python, in order to analyze and classify the success of charitable donations. Following methods were used for the anlaysis:
  * A charity dataset was provided and we preprocessed the data for the neural network model,
  * Then we did compile, train and evaluate the model.
  * Next we optimized the model.

## Resources
* Data Source: charity_data.csv
* Software: Python 3.7.7, Anaconda Navigator 1.9.12, Conda 4.8.4, Jupyter Notebook 6.0.3

## Results:  

### Data Preprocessing - 

* The columns EIN and NAME are identification information and have been removed from the input data.
* The column IS_SUCCESSFUL is considered as the target feature as it contains binary data referring to whether or not the charity donation was used effectively.  
* The columns APPLICATION_TYPE, AFFILIATION, CLASSIFICATION, USE_CASE, ORGANIZATION, STATUS, INCOME_AMT, SPECIAL_CONSIDERATIONS, ASK_AMT are considered as the features for our model.
* Next we performed encoding of categorical variables.
* Next we split the data into training and testing datasets.
* The datasets were scaled using StandardScaler.



### Compiling, Training, and Evaluating the Model - 
The Feature ASK_AMT had 8747 unique values which is way more than 10, so in order to enhance the performance of the model, we applied binning method to this feature and organized the different values by ranges.

#### First Attempt
* This deep-learning neural network model is made of two hidden layers with 80 and 30 neurons respectively.
* The input data has 52 features.
* The output layer is made of one neuron as it is a binary classification.
* We used the activation function tanh for the hidden layers. As our output is a binary classification, Sigmoid is used on the output activation function.
* For the compilation, the optimizer is adam and the loss function is binary_crossentropy.
* The epoch or iterations were set to 100 in this scenario. 
* The model accuracy is 0.723498523235321 which is under 75%. 

![image](https://user-images.githubusercontent.com/3753839/184272334-e76a1fc7-3ae1-469e-b0e1-fe9966246383.png)

*	This is not a good performance to help predict the outcome of the charity donations so will try another method.
	
#### Second Attempt
* This deep-learning neural network model is made of two hidden layers with increased number of neurons than the first attempt, 100 and 50 neurons respectively.
* The input data still has 52 features.
* The output layer is made of one neuron as it is a binary classification.
* Here we used a different activation function ReLU for the hidden layers. As our output is a binary classification, Sigmoid is used as the output activation function.
* For the compilation, the optimizer is adam and the loss function is binary_crossentropy.
* The epoch or iterations are set to 100 in this scenario. 
* The model accuracy is this case is 0.726064145565033 which is still it's under 75%. 

![image](https://user-images.githubusercontent.com/3753839/184272266-e94a8c01-9312-4dff-94e2-8b4b87969ec1.png)
	
* This also is not a satisfying performance to help predict the outcome of the charity donations, so we will try another time.
	
#### Third Attempt
* This deep-learning neural network model is made of three hidden layers with 100 , 80 and 30 neurons respectively.
* The input data still has 52 features.
* The output layer is made of one neuron as it is a binary classification.
* Here we are again using the activation function ReLU for the hidden layers. As our output is a binary classification, Sigmoid is used as the output activation function.
* For the compilation, the optimizer is adam and the loss function is binary_crossentropy.
* The epoch or iterations were also increased to 150 in this scenario. 
* The model accuracy is 0.727580189704895 which is again under 75%. 

![image](https://user-images.githubusercontent.com/3753839/184272185-45f4982e-6916-43ca-8242-834075b1778f.png)

	
* So none of these attempts gave a satisfying performance to help predict the outcome of the charity donations.
	

### Summary: 
As we see the results above. the deep learning neural network model did not reach the target of 75% accuracy in the first 3 attempts. 
Considering that this target level is pretty average we could say that the model is not outperforming.
In this scenario it’s a binary classification situation, so we can try using a supervised machine learning model such as Random Forest Classifier to combine a multitude of decision trees to generate a classified output and compare its accuracy against our deep learning model. 
