# Coding-Layers-in-Neural-Networks-From-Scratch
This notebook provides a beginner-friendly, step-by-step implementation of neurons and layers in a neural network using pure Python (no libraries like NumPy or TensorFlow initially). It demystifies how neural networks compute forward passes at the core level.

---

##  Objectives

- Understand how **individual neurons** compute outputs from inputs, weights, and biases.
- Build **multiple neurons (a layer)** and perform matrix-style computation manually.
- Learn how biases and weights contribute to each neuron's output.
- Observe how these concepts scale from **a single neuron → full layers → multiple layers**.

---

##  Structure and Analysis

###  Step 1: Single Neuron (3 Inputs)
```python
inputs = [1, 2, 3]
weights = [0.2, 0.8, -0.5]
bias = 2
output = inputs[0]*weights[0] + inputs[1]*weights[1] + inputs[2]*weights[2] + bias
This block simulates a basic neuron:

Takes 3 input features.

Multiplies each with a weight.

Adds them up and adds a bias.

Prints the scalar output.

 Step 2: Single Neuron (4 Inputs)
python
Copy
Edit
inputs = [1.0, 2.0, 3.0, 2.5]
weights = [0.2, 0.8, -0.5, 1.0]
bias = 2.0
output = (inputs[0]*weights[0] +
          inputs[1]*weights[1] +
          inputs[2]*weights[2] +
          inputs[3]*weights[3] + bias)
Extended the previous example:

Shows how neurons handle more features (4 inputs now).

Output is still a single value.

 Step 3: One Layer with 3 Neurons
python
Copy
Edit
inputs = [1, 2, 3, 2.5]
weights = [
 [0.2, 0.8, -0.5, 1],
 [0.5, -0.91, 0.26, -0.5],
 [-0.26, -0.27, 0.17, 0.87]
]
biases = [2, 3, 0.5]

outputs = [
    # Neuron 1:
    inputs[0]*weights[0][0] + inputs[1]*weights[0][1] +
    inputs[2]*weights[0][2] + inputs[3]*weights[0][3] + biases[0],

    # Neuron 2:
    inputs[0]*weights[1][0] + inputs[1]*weights[1][1] +
    inputs[2]*weights[1][2] + inputs[3]*weights[1][3] + biases[1],

    # Neuron 3:
    inputs[0]*weights[2][0] + inputs[1]*weights[2][1] +
    inputs[2]*weights[2][2] + inputs[3]*weights[2][3] + biases[2]
]
Here, we:

Introduce a layer with multiple neurons.

Each neuron has its own weights and bias.

Computes an output vector with 3 values—one for each neuron.

