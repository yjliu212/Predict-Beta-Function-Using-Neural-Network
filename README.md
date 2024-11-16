# Predict-Beta-Function-Using-Deep-Neural-Network

Beta function is a diagenesis function modeled using Arrhenius equation. It represents the diagenesis of smectite rich shale to illite rich shale as a function of depth with elevated burial age and temperature. As described in Dutta et al., (2022), chapter 3.4, Chemical Diagenesis as a Geopressure Mechanism, Beta function is a function of burial age and temperature as shown in the picture below.
![image](https://github.com/user-attachments/assets/53517f01-49eb-41a4-b470-d714f6d9a922)

Here, we are using Deep Neural Network (DNN) to model the Beta function.

The features selected for the training dataset are Depth_BML (depth below mud line), Temperature, Age, and the target is Beta
<img width="319" alt="image" src="https://github.com/user-attachments/assets/7041b3ce-1092-4b74-ba37-e48d85f7acc9">

We have three senarios of training datasets:

*  Training dataset 1: A single Beta function with a fixed thermal gradient and burial rate
*  Training dataset 2: 100 Beta functions with Temperature from 100 randomly sampled thermal gradients and a fixed burial rate 
*  Training dataset 3: 100 Beta functions with Temperature and Age from 10 randomly sampled thermal gradients and 10 randomly sampled burial rate

Through this experiment, we can see that the DNN model from training 1 and 2 will under-predict the target Beta function, no matter how many epochs we traing the DNN model. This means that the DNN model is not generalized enough, because the training dataset does not contain enough variance to cover all the feature space. 

After training with dataset 3, we can see that the DNN model is capable of predicting Beta functions for new input features. Now the DNN model is well generalized to make predictions, no longer under-predicting.

