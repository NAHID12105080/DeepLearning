# Backpropagation in Neural Networks

Backpropagation is an algorithm used to train neural networks by updating the weights and biases to minimize the error (loss) between the predicted and actual outputs. It involves two main steps: **forward propagation** to compute the output, and **backward propagation** to update the weights using the gradients of the loss function.

## 1. Understanding the Loss Function

The loss function measures the error between the predicted output (\( \hat{y} \)) and the actual output (\( y \)). For simplicity, we use the Mean Squared Error (MSE) as the loss function:

    L = (1/2) * Σ (ŷ_i - y_i)^2

Where:
- **ŷ_i** is the predicted output
- **y_i** is the actual output
- **n** is the number of samples

## 2. Key Concepts of Backpropagation

### Gradient Descent

To minimize the loss function, we use **gradient descent**, an optimization technique that updates the weights and biases in the direction that reduces the loss. The update rule for weights (w) and biases (b) is:

    w = w - η * (∂L/∂w)
    b = b - η * (∂L/∂b)

Where:
- **η** is the learning rate
- **∂L/∂w** and **∂L/∂b** are the gradients of the loss function with respect to the weights and biases

### Chain Rule

Backpropagation uses the **chain rule** to calculate gradients for each weight in the network, layer by layer, starting from the output layer and moving backward.

## 3. Mathematical Derivation

Let’s derive the gradient of the loss function with respect to the weights. Suppose we have:

- **Output layer activation**: a^[L] = ŷ
- **Loss function**: L = (1/2) * (ŷ - y)^2

### Step 1: Compute the Error at the Output Layer

The derivative of the loss with respect to the output (ŷ) is:

    ∂L/∂a^[L] = ŷ - y

### Step 2: Compute the Gradient for the Output Layer Weights

Using the chain rule, the gradient with respect to the weight (w^[L]) is:

    ∂L/∂w^[L] = (∂L/∂a^[L]) * (∂a^[L]/∂z^[L]) * (∂z^[L]/∂w^[L])

Where:
- **z^[L]** is the weighted sum for the output layer: z^[L] = w^[L] * a^[L-1] + b^[L]
- **a^[L-1]** is the activation from the previous layer

### Step 3: Backpropagate the Error to Previous Layers

Repeat the above steps for each layer, moving backward, updating each layer's weights and biases using their respective gradients.

## 4. Implementation of Backpropagation (Python Example)

Here’s a simple implementation of backpropagation in Python using NumPy:

```python
import numpy as np

# Sigmoid activation function
def sigmoid(z):
    return 1 / (1 + np.exp(-z))

# Derivative of sigmoid
def sigmoid_derivative(a):
    return a * (1 - a)

# Initialize weights, biases, learning rate
np.random.seed(0)
weights = np.random.randn(2, 1)
bias = np.random.randn(1)
learning_rate = 0.1

# Training data
X = np.array([[0, 0], [0, 1], [1, 0], [1, 1]])
y = np.array([[0], [1], [1], [0]])

# Training loop
for epoch in range(10000):
    # Forward propagation
    z = np.dot(X, weights) + bias
    a = sigmoid(z)
    
    # Compute the loss (MSE)
    loss = np.mean(0.5 * (a - y) ** 2)
    
    # Backward propagation
    dz = (a - y) * sigmoid_derivative(a)
    dw = np.dot(X.T, dz) / len(X)
    db = np.sum(dz) / len(X)
    
    # Update weights and biases
    weights -= learning_rate * dw
    bias -= learning_rate * db
    
    # Print loss every 1000 epochs
    if epoch % 1000 == 0:
        print(f'Epoch {epoch}, Loss: {loss:.4f}')
```
### 5. Summary
- Backpropagation calculates the gradient of the loss function with respect to each weight by applying the chain rule.
- Gradient descent updates the weights in the direction that reduces the loss.
- The process repeats for a specified number of epochs until the network converges to a minimum error.
