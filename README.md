

# Neural Network Classifier for Charity Success Prediction

## Overview

This project aims to create a deep learning model to predict the success of charity applications based on various features. The model can assist in determining which organizations are worth investing in.

## Data Preprocessing

### Dataset
The dataset contains information about various charities, including their affiliations, classifications, use cases, organization type, income amount, ask amount, and success status.

### Preprocessing Steps
1. **Dropping Unnecessary Columns**: The columns 'EIN' and 'NAME' were identified as non-beneficial and were dropped from the dataset.
   ```python
   application_df.drop(columns=["EIN"], inplace=True)
   ```
2. **Target Variable**: The "IS_SUCCESSFUL" column is used as the target for the prediction. Its distribution was checked to ensure there are no major imbalances.
   ```python
   application_df["IS_SUCCESSFUL"].value_counts()
   ```
3. **Feature Encoding**: Categorical variables were encoded using techniques such as one-hot encoding.
4. **Scaling**: The features were scaled to ensure that they have similar ranges.

## Model Architecture

The neural network model was created using TensorFlow and Keras. The architecture includes:
- Input layer with dimensions matching the number of features.
- Two hidden layers:
  - First hidden layer with 1.5 times the number of input features.
  - Second hidden layer with 0.75 times the number of input features.
- Output layer with a sigmoid activation function, suitable for binary classification.

## Training

The model was trained using the following parameters:
- Loss function: Binary cross-entropy.
- Optimizer: Adam.
- Metrics: Accuracy.
- Number of epochs: 100.

## Evaluation

The trained model was evaluated on a test set, achieving an accuracy improvement from 72% to 75% after the code modification.

```python
model_loss, model_accuracy = nn.evaluate(X_test_scaled, y_test, verbose=2)
print(f"Loss: {model_loss}, Accuracy: {model_accuracy}")
```

## Conclusion

This project demonstrates the application of deep learning techniques to the classification of charity success. By careful preprocessing and model tuning, the accuracy was improved, showcasing the potential of neural networks in real-world problem-solving.
