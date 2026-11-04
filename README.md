# LSTM Time Series Prediction

## 1. Project Description
This project uses a Long Short-Term Memory (LSTM) neural network to predict the next value in a time series dataset.

The dataset is generated using a sine wave, a linear trend, and random noise. The LSTM model learns patterns from previous observations and predicts future values.

## 2. Technologies Used
- Python
- NumPy
- Matplotlib
- TensorFlow / Keras

## 3. Dataset
- Total data points: 1000
- Training split: 80%
- Testing split: 20%
- Window size: 30
- Random seed: 42

## 4. Implementation Steps

### Task 1: Data Scaling
The minimum and maximum values are calculated using only the training portion of the series. These statistics are then used to scale the series.

### Task 2: Sliding Windows
A sliding window of 30 values is created. Each window is used to predict the value immediately after it.

### Task 3: Reshaping and Splitting
The input data is reshaped to three dimensions:

`(samples, time_steps, features)`

The data is split in chronological order, with earlier windows used for training and later windows used for testing.

### Task 4: LSTM Model
The model contains:
- An LSTM layer with 50 units
- A Dense output layer with 1 neuron

### Task 5: Training and Evaluation
The model is trained using:
- Optimizer: Adam
- Loss function: MSE
- Metric: MAE
- Epochs: 20
- Batch size: 32

The final predictions are evaluated using RMSE (Root Mean Squared Error).

## 5. Expected Output
When the program runs, it displays:
- Training progress for 20 epochs
- Training loss and MAE
- Validation loss and validation MAE
- The final Test RMSE value

Example format:

```text
Epoch 1/20
...
Epoch 20/20
...
Test RMSE: <calculated value>
```

The exact RMSE value may vary depending on the TensorFlow version and execution environment.

## 6. How to Run the Project

### Step 1: Install the required libraries

```bash
pip install numpy matplotlib tensorflow
```

### Step 2: Save the Python program
Save the completed code in a file named `main.py`.

### Step 3: Run the program

```bash
python main.py
```

## 7. Conclusion
This project demonstrates how an LSTM neural network can learn sequential patterns from time-series data and predict future values using sliding windows. It also demonstrates data scaling, chronological train-test splitting, model training, and evaluation using RMSE.
