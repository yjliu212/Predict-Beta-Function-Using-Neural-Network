# Predict-Beta-Function-Using-Deep-Neural-Network

## [Notebook:](Assignment_2b_Beta_Function_Prediction.ipynb)

In this Python Jupyter Notebook, we train a Deep Neural Network (DNN) to compute the diagenesis Beta function, a critical component in pore pressure prediction, particularly in high-temperature, high-pressure environments. The DNN model consists of three fully connected layers: the input layer with 64 nodes, a hidden layer with 16 nodes, and an output layer with a single node representing the Beta value.

## Introduction:

Beta function is a diagenesis function modeled using Arrhenius equation. It represents the diagenesis of smectite rich shale to illite rich shale as a function of depth with elevated burial age and temperature. As described in Dutta et al., (2022), chapter 3.4, Chemical Diagenesis as a Geopressure Mechanism, Beta function is a function of burial rate and temperature gradient as shown in the picture below.

![image](https://github.com/user-attachments/assets/53517f01-49eb-41a4-b470-d714f6d9a922)

## Deep Neural Network:

In this Notebook, we will use Deep Neural Network (DNN) to model the Beta function.

The training datasets contains three features: Depth_BML (depth below mud line), Temperature, Age, and the calculated Beta is the target.

The dataset is splited into 70% as training part and 30% as testing part.

<img width="319" alt="image" src="https://github.com/user-attachments/assets/7041b3ce-1092-4b74-ba37-e48d85f7acc9">

## Training Datasets:

We have three senarios of training datasets:

*  Training dataset 1: A single Beta function with a fixed thermal gradient and fixed burial rate
*  Training dataset 2: 100 Beta functions with Temperature from 100 randomly sampled thermal gradients and a fixed burial rate 
*  Training dataset 3: 100 Beta functions with Temperature and Age from 10 randomly sampled thermal gradients and 10 randomly sampled burial rate

## Results:

**Results using training dataset 1:**

![image](https://github.com/user-attachments/assets/7063f062-0a49-402d-b0f7-debb78ee0e96)

Training result show good match based on 30% of the training dataset

![image](https://github.com/user-attachments/assets/f2e853be-e8ee-4ba6-b938-c575ebf62a06)

But the trained DNN model fails to predict a new dataset using a different thermal gradient

*Results using training dataset 2:**


  
*Results using training dataset 3:**
  
## Discussion:

Through this experiment, we can see that the DNN model from training dataset 1 and 2 always under-predict the target Beta function. No matter how many epochs we train the DNN model using dataset 1 and 2, the DNN model can only predict the testing data well but not able to predict a new input dataset with a different thermal gradient or burial rate. This means that the DNN model is not generalized enough, due to the training dataset does not contain enough feature variance. 

However, after training with dataset 3, we can see that the DNN model is capable to predict Beta functions for the new input data. This means that now the DNN model is well generalized to make correct predictions, with no under-prediction.

## Reference:

NADER C. DUTTA, RAN BACHRACH AND TAPAN MUKERJI, 2022, QUANTITATIVE ANALYSIS OF  GEOPRESSURE  FOR GEOSCIENTISTS  AND ENGINEERS.
