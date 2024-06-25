# Deep Learning Challenge

## Overview of the Analysis

The purpose of this analysis is to create a binary classifier using deep learning techniques to predict whether applicants funded by Alphabet Soup will be successful in their ventures. This has the potential to help to optimize funding decisions by determining which applicants have the best chance of success, thereby maximizing the impact of financial support.

## Results

### Data Preprocessing

#### What variable(s) are the target(s) for your model?

- **IS_SUCCESSFUL**: This is the target value for the model indicating whether the funded project was successful.
   
#### What variable(s) are the features for your model?

- **APPLICATION_TYPE**: Type of application.
- **AFFILIATION**: Affiliated sector of industry.
- **CLASSIFICATION**: Government organization classification.
- **USE_CASE**: Use case for funding.
- **ORGANIZATION**: Organization type.
- **INCOME_AMT**: Income classification.
- **ASK_AMT**: Funding amount requested.
- **SPECIAL_CONSIDERATIONS**: Special considerations for the application.
- **STATUS**: Active status.

#### What variable(s) should be removed from the input data because they are neither targets nor features?

- **EIN**: Employer Identification Number, a unique identifier for organizations.
- **NAME**: Name of the organization.

In the AlphabetSoupCharity_Optimized2 optimization attempt, these additional variables were removed:

- **SPECIAL_CONSIDERATIONS**: Special considerations for the application.
- **STATUS**: Active status.

### Compiling, Training, and Evaluating the Model

#### How many neurons, layers, and activation functions did you select for your neural network model, and why?

The model was designed with a varying number of input features, starting with the initial set of features and then removing non-beneficial columns, adding hidden layers and using a mix of activation functions.

- **Hidden Layers**: Different configurations of hidden layers were tested:
  - **First Attempt**: Two hidden layers with 80 and 30 neurons respectively, using ReLU activation functions.
  - **Second Attempt**: Three hidden layers with 100, 50, and 25 neurons, adding complexity to the model.
  - **Third Attempt**: Three hidden layers with 100, 50, and 25 neurons.
  - **Fourth Attempt**: Three hidden layers with 150, 100, and 50 neurons, adding complexity to the model.
    
- **Output Layer**: One output neuron with a sigmoid activation function for binary classification.

- **Activation Functions**: A mix of ReLU, tanh, and elu activation functions were used in different layers to test their effects on model performance.

#### Were you able to achieve the target model performance?

No, the model performed as follows:

- **First Attempt**: 
  - **Accuracy**: ~72.52%
  - **Loss**: ~0.564
- **Second Attempt**: 
  - **Accuracy**: ~72.58%
  - **Loss**: ~0.579
- **Third Attempt**: 
  - **Accuracy**: ~72.74%
  - **Loss**: ~0.574
- **Fourth Attempt**: 
  - **Accuracy**: ~72.53%
  - **Loss**: ~0.592


#### What steps did you take in your attempts to increase model performance?

1. **Adjust Input Data**: 
   - Grouped rare occurrences in categorical variables as "Other".
   - Dropped non-beneficial columns like `EIN` and `NAME`, and later `STATUS` and `SPECIAL_CONSIDERATIONS`.

2. **Model Architecture Adjustments**:
   - Increased the number of neurons in hidden layers.
   - Added additional hidden layers to increase model depth.
   - Experimented with different activation functions (`relu`, `tanh`, `elu`).

3. **Training Adjustments**:
   - Adjusted learning rates and batch sizes.
   - Increased the number of epochs.
   

## Summary

The final model did not achieve the target performance of 75% accuracy, with the best attempt reaching approximately 72.74% accuracy. Various techniques were used to optimize the model.
