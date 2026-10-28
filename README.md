# XOR Neural Network Implementation

This notebook demonstrates how to solve the **XOR (exclusive OR) problem** using a multilayer perceptron (MLP) in two ways:

1. **From scratch using NumPy**
2. **Using Keras with TensorFlow**

## Dataset

The notebook uses four binary input combinations and their XOR outputs:

| Input 1 | Input 2 | XOR Output |
|---:|---:|---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

XOR returns `1` when the two inputs differ and `0` when they are the same.

## Implementations

### 1. NumPy implementation

The first code cell builds and trains a small MLP without a deep-learning framework.

- **Architecture:** 2 input neurons, 2 hidden neurons, and 1 output neuron
- **Activation:** Sigmoid in the hidden and output layers
- **Learning rate:** `0.1`
- **Training epochs:** `10,000`
- **Training method:** Forward propagation, error calculation, backpropagation, and weight/bias updates
- **Output:** Prints the predicted outputs for the four XOR inputs

Weights and biases are initialized randomly, so the exact predictions can vary between runs.

### 2. Keras / TensorFlow implementation

The second code cell builds the model using TensorFlow's Keras API.

- **Architecture:** 2 input features, a hidden Dense layer with 8 neurons, and a 1-neuron output layer
- **Hidden activation:** ReLU
- **Output activation:** Sigmoid
- **Loss function:** Binary cross-entropy
- **Optimizer:** Stochastic Gradient Descent (SGD)
- **Learning rate:** `0.1`
- **Training epochs:** `1,000`
- **Evaluation:** Prints model accuracy
- **Prediction:** Prints predictions rounded to `0` or `1`

Because training starts from random initial weights, accuracy and predictions may vary between runs.

## Requirements

- Python 3
- NumPy
- TensorFlow

## Installation

Install the required packages with:

```bash
pip install numpy tensorflow
```

## How to Run

1. Open `lab1.ipynb` in Jupyter Notebook, JupyterLab, or Google Colab.
2. Make sure the required packages are installed.
3. Run the notebook cells in order.
4. Review the predicted XOR outputs from the NumPy implementation and the accuracy and rounded predictions from the Keras implementation.

## Expected Result

Both implementations are intended to learn the XOR mapping:

```text
Input [0, 0] -> 0
Input [0, 1] -> 1
Input [1, 0] -> 1
Input [1, 1] -> 0
```

The exact printed values may differ because the models use randomly initialized parameters. The NumPy version prints sigmoid probabilities; the Keras version also prints predictions rounded to binary values.

## Learning Objectives

- Understand the XOR problem and why a hidden layer is useful for learning it.
- Learn the basics of a multilayer perceptron.
- Understand forward propagation and backpropagation.
- Compare a manually implemented neural network with a Keras/TensorFlow model.
- Train, evaluate, and test a simple binary-output neural network.
