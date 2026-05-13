# Part 1: Neural Network Fundamentals and Training Behavior Analysis

## Dataset
Source: https://drive.google.com/drive/folders/1akV6po4Nrgkc3yQrJkzA6cJIV-wBvUYs

## Overview
Built a feed-forward neural network on a structured dataset to demonstrate
forward pass, loss calculation, backpropagation, and weight updates.

## Steps
1. Dataset exploration (shape, types, missing values, distribution)
2. Preprocessing (missing value handling, encoding, StandardScaler)
3. Feed-forward NN with 2 hidden layers, ReLU, Dropout
4. Training with Early Stopping; plotted loss and accuracy curves
5. Five hyperparameter experiments compared in a table

## Results
| Experiment | Layers | Neurons | LR | Activation | Test AUC-ROC |
|---|---|---|---|---|---|
| Exp 1: Baseline | 2 | 64 | 0.001 | relu | 0.9112 |
| Exp 2: More Neurons | 2 | 128 | 0.001 | relu | 0.8794 |
| Exp 3: Higher LR | 2 | 64 | 0.010 | relu | 0.9036 |
| Exp 4: Deeper Network | 3 | 64 | 0.001 | relu | 0.8964 |
| Exp 5: Tanh+Large Batch | 2 | 64 | 0.001 | tanh | 0.9336 |

## Key Observations
- Best configuration: Based on 'Test AUC-ROC', 'Exp 5: Tanh+Large Batch' (2 layers, 64 neurons, tanh, LR=0.001, Batch=64) achieved the best performance with an AUC-ROC of 0.9336. The baseline model and other experiments showed slightly lower or comparable performance. This suggests that for this dataset, a tanh activation function and a larger batch size might be beneficial.
- Overfitting / underfitting signs: The training and validation loss/accuracy curves show that the model generalizes well. Both training and validation accuracies are high and very close (e.g., train accuracy ~0.9830, val accuracy ~0.9812), and the losses decrease similarly. This indicates that the model is neither significantly overfitting (where training performance would be much better than validation) nor underfitting (where both would be low).
