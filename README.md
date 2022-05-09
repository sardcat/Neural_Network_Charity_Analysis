# Neural Network Charity Analysis
Neural Networks and Deep Learning Models

## Overview
Using Tensorflow in Jupyter Notebook, "the Team" delved into deep machine learning models to predict success for charity campaigns submitted to
the orginization Alphabet Soup Charity.

## Results
### Data Preprocessing

Figure 1.) Features Given from .CSV File.

![](Resources/Fig1.png)

* The target variable in the provided data set is "IS_SUCCESSFUL".
* Initial feature variables include: "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS" and "ASK_AMT".
* Cursory visual analysis revealed that "EIN" and "NAME" would play no role in modeling, hence were dropped.

### Compiling, Training, and Evaluating the Model

Figure 2.) Initial Deep Neural Net Parameters.

![](Resources/Fig2.png)

* In the initial model setup the input layer had 80 neurons with the "RELU" activation function, one hidden layer of 30 neurons with the activation function "RELU" and an output layer with the "SIGMOID" activation function.
* The model was run over 100 epochs.

Figure 3.) Model Loss & Accuracy results over 100 Epochs.

![](Resources/Fig3.png)

* The model's goal was 75%+ accuracy, which the initial model fell short of by only reaching 72.5%.
* To improve model performance, the following changes were implimented:
  - The "STATUS" column was dropped due to its value being uniform (1) over 95% of the dataset.
  - Binning size for "Other" in "APPLICATION_TYPE" and "CLASSIFICATION" was increased to reduce the number of inputs.
  - Input layer neurons were increased to 200 with an activation function of "TANH".
  - A total of 3 hidden layers was implimented, all with the activation function "RELU" and a stepped neuron count of 175, 150 and 125.
  - The number of epochs performed was increased to 200.

Figure 4.) Optimized Model Loss & Accuracy over 200 Epochs.

![](Resources/Fig4.png)

* Implimented optimization changes further decreased the model's accuracy to 72.2%
