# Forward Propagation in Neural Networks

Forward propagation is the process by which input data passes through a neural network to produce an output. It involves computing the output of each layer sequentially, starting from the input layer and ending at the output layer. Here's how it works step by step:

## 1. Structure of a Neural Network

A typical neural network consists of:
- **Input layer**: Receives the input features.
- **Hidden layers**: Perform computations on the inputs.
- **Output layer**: Produces the final prediction.

Each layer contains **neurons**, which are connected to the neurons of the previous layer. The connections have associated **weights** and **biases**.

## 2. Steps of Forward Propagation

### Step 1: Compute the Weighted Sum
For each neuron in the hidden and output layers, compute the weighted sum of the inputs:

    z = Σ (w_i * x_i) + b

Where:
- **w_i** are the weights
- **x_i** are the inputs
- **b** is the bias
- **n** is the number of inputs

### Step 2: Apply the Activation Function
The weighted sum is then passed through an **activation function** to introduce non-linearity into the model:

    a = σ(z)

Where:
- **σ** is the activation function (e.g., ReLU, sigmoid, or tanh)
- **a** is the activated output (also known as the neuron’s output)

### Step 3: Repeat for Each Layer
Repeat the above steps for each hidden layer until you reach the output layer.

## 3. Example of Forward Propagation

Suppose we have a simple neural network with:
- **2 input features** (x1, x2)
- **1 hidden layer** with 2 neurons
- **1 output neuron**

### Given:
- Weights: w_11, w_12, w_21, w_22 for the hidden layer and w_o1, w_o2 for the output neuron
- Biases: b_1, b_2 for the hidden layer and b_o for the output layer

### Forward Propagation Process:
1. Compute the weighted sum for each hidden layer neuron:

       z_1 = w_11 * x_1 + w_12 * x_2 + b_1
       z_2 = w_21 * x_1 + w_22 * x_2 + b_2

2. Apply the activation function (e.g., ReLU):

       a_1 = ReLU(z_1)
       a_2 = ReLU(z_2)

3. Compute the weighted sum for the output neuron:

       z_o = w_o1 * a_1 + w_o2 * a_2 + b_o

4. Apply the activation function for the output (e.g., sigmoid):

       ŷ = sigmoid(z_o)

## 4. Activation Functions

Common activation functions include:
- **ReLU (Rectified Linear Unit)**: ReLU(z) = max(0, z)
- **Sigmoid**: sigmoid(z) = 1 / (1 + e^(-z))
- **Tanh**: tanh(z) = (e^z - e^(-z)) / (e^z + e^(-z))

## 5. Summary

Forward propagation involves:
- Calculating the weighted sums for each layer.
- Applying activation functions to introduce non-linearity.
- Propagating the outputs layer by layer to obtain the final prediction.

This process enables the neural network to map input features to the desired output.
