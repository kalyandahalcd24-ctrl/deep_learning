# Comparing Batch Gradient Descent and Mini-Batch SGD

## Overview

This notebook compares two training strategies for a binary classification neural network using the **two-moons dataset**. It builds the same multilayer perceptron architecture for each experiment and compares their accuracy after training.

## Dataset and Preprocessing

- **Dataset:** Two-moons dataset generated with `sklearn.datasets.make_moons`
- **Number of samples:** 400
- **Noise:** `0.20`
- **Random state:** `1`
- **Features:** 2 input features per sample
- **Labels:** Binary labels reshaped to a column vector
- **Preprocessing:** Features are standardized by subtracting each feature's mean and dividing by its standard deviation

## Model Architecture

Both experiments use the same neural network:

- Input layer: 2 features
- Hidden layer 1: 16 neurons, ReLU activation
- Hidden layer 2: 16 neurons, ReLU activation
- Output layer: 1 neuron, sigmoid activation

The model is compiled with binary cross-entropy loss and stochastic gradient descent (SGD) as the optimizer. Accuracy is used as the evaluation metric.

## Experiments

### 1. Batch Gradient Descent

- Learning rate: `0.5`
- Epochs: `200`
- Batch size: `400` (the full dataset in one batch)
- Output: Prints the model's training-set accuracy as `Batch GD Accuracy`

### 2. Mini-Batch SGD

- Learning rate: `0.1`
- Epochs: `200`
- Batch size: `16`
- Output: Prints the model's training-set accuracy as `SGD Accuracy`

The TensorFlow random seed is set to `0` before building and training each model.

## Requirements

- Python 3
- NumPy
- TensorFlow
- scikit-learn

## Installation

Install the required packages:

```bash
pip install numpy tensorflow scikit-learn
```

## How to Run

1. Open `Untitled10.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
2. Install the required packages if they are not already installed.
3. Run the notebook cell.
4. Compare the printed accuracy values for Batch Gradient Descent and Mini-Batch SGD.

## Expected Output

The notebook prints two accuracy values, for example:

```text
Batch GD Accuracy : <measured accuracy>
SGD Accuracy      : <measured accuracy>
```

The actual values are produced when the notebook runs and are not specified in advance. The notebook evaluates each model on the same data used for training, so these values are training-set accuracy rather than held-out test accuracy.

## Learning Objectives

- Understand the difference between full-batch and mini-batch training.
- Observe how batch size and learning rate are configured in neural-network training.
- Build and train a binary classification model with TensorFlow/Keras.
- Compare training-set accuracy from two gradient-descent approaches.
