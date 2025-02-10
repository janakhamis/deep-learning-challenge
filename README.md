# deep-learning-challenge

**Report on the Neural Network Model for Alphabet Soup**

## Overview of the Analysis
The purpose of this analysis is to create a deep learning model that can predict the success of funding proposals submitted to Alphabet Soup, a charitable organization. The model's goal is to find critical factors that impact funding approval and optimize its performance for better predictive accuracy.

## Results
### Data Preprocessing
- **Target Variable:** The target variable for the model is the `IS_SUCCESSFUL` column, which indicates whether the funding application was approved.
- **Feature Variables:** The features used for training include various categorical and numerical columns that describe the organization, application type, amount requested, and other relevant attributes.
- **Removed Variables:** Some columns, such as `EIN` and `NAME`, were removed as they are identifiers and do not contribute to the predictive power of the model.

### Compiling, Training, and Evaluating the Model
- **Neural Network Architecture:**
  - The model consists of multiple dense layers:
    - Input layer with the appropriate number of neurons corresponding to the number of features.
    - Two hidden layers with 80 and 30 neurons, respectively, using the ReLU activation function.
    - An output layer with a single neuron using the sigmoid activation function to classify applications as successful or unsuccessful.
    ![alt text](image.png)
- **Model Performance:**
  - The initial model achieved an accuracy of approximately 73.52%, which did not meet the desired target performance.

- **Optimization Attempts:**

    To improve the model's accuracy, three different optimization strategies were tested:  

    #### **Optimization 1: Increasing Neurons and Adding a Hidden Layer**  
    - **Increased the number of neurons** in each hidden layer to enhance learning capacity (100, 80, and 30 neurons respectively).  
    - **Added an additional hidden layer** to increase model complexity and allow for more intricate pattern recognition.  
    ![alt text](image-1.png)

    #### **Optimization 2: Adjusting Hidden Layer Neurons & Increasing Training Duration**  
    - **Adjusted the number of neurons** in the first and second hidden layers to evaluate the impact on performance (90 and 50 neurons respectively).
    - **Increased the number of epochs to 120** to allow the model more time to learn from the data.  
    - **Monitored validation loss** to detect overfitting and determine if early stopping was necessary. 
    ![alt text](image-2.png) 

    #### **Optimization 3: Simplifying the Network Architecture**  
    - **Removed the third hidden layer** to simplify the network architecture and reduce the risk of overfitting.
    - **Retained the adjusted number of neurons** in the first and second hidden layers (90 and 50 neurons respectively) to maintain a balance between learning capacity and model complexity.
    ![alt text](image-3.png)

## Summary
The results indicate that increasing the model's complexity did not substantially improve its performance, with accuracy remaining steady at approximately 73%. This suggests that the dataset may have reached its limit in capturing meaningful patterns, and the current features may be maximizing the predictive power achievable with this model.

Adding more neurons and layers did not yield noticeable improvements, implying that increasing model complexity may not be the most effective strategy. Instead, focusing on enhancing data quality through improved feature selection, additional feature engineering, and experimenting with different data preparation techniques may lead to better results.

Moreover, there is a risk of model overfitting, even if it is not immediately evident from the test accuracy. Re-examining feature scaling, encoding strategies, and feature importance analysis could provide further opportunities to boost model performance.

To address the current limitations, numerous ways are proposed. Consider using Tree-Based Models, such as Random Forest or Gradient Boosting (e.g., XGBoost), to effectively handle categorical variables, capture non-linear correlations, and offer feature significance insights for improved feature selection. Alternatively, a Support Vector Machine (SVM) with a non-linear kernel (e.g., RBF) can enhance performance in circumstances when classes overlap. Furthermore, hyperparameter tweaking with tools like Keras Tuner or Grid Search may optimize parameters like the number of neurons, learning rate, batch size, and dropout rate, resulting in improved model performance.