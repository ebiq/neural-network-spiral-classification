# C++ Neural Network From Scratch for Nonlinear Classification

## Project Overview

This project implements a fully connected neural network (Multi-Layer Perceptron, MLP) from scratch using C++ for binary classification tasks.

Instead of using existing deep learning frameworks such as TensorFlow or PyTorch, the project focuses on understanding the mathematical and algorithmic foundations of neural networks, including:

- Feed Forward
- Backpropagation
- Stochastic Gradient Descent (SGD)
- Nonlinear Activation Functions
- Deep Network Representation Learning
- Decision Boundary Learning and Visualization

The model is tested on both:

- Simple linear binary classification datasets
- Spiral nonlinear classification datasets

to study how network depth affects nonlinear function learning capability.

---

# Project Objectives

The main objectives of this project are:

- Build a neural network training framework from scratch
- Understand how neural networks learn classification functions
- Implement Backpropagation manually
- Compare shallow and deep network representation capability
- Learn complex nonlinear decision boundaries
- Visualize neural network classification results

---

# Core Idea of Neural Networks

The neural network essentially learns a continuous function:

```text
F(x,y)
```

For any point in a 2D plane:

- If `F(x,y) > 0`, the point belongs to the red class
- If `F(x,y) < 0`, the point belongs to the blue class

The network does not directly “draw” decision boundaries.

Instead, it learns the function distribution over the entire input space.

The decision boundary is simply the region where:

```text
F(x,y)=0
```

---

# Project Implementation

## 1. Fully Connected Neural Network (MLP)

Implemented configurable multilayer neural network architectures such as:

```text
2 → 4 → 4 → 1
```

and:

```text
2 → 4 → 4 → 4 → 1
```

Where:

- Input Layer: 2D coordinates `(x,y)`
- Hidden Layers: Learn nonlinear feature representations
- Output Layer: Predicts function value `F(x,y)`

---

## 2. Feed Forward

The neural network performs prediction through:

```text
z = Wx + b
a = tanh(z)
```

Each layer repeatedly applies:

- Linear transformation
- Nonlinear activation

The final output:

```text
F(x,y)
```

is used for classification.

---

## 3. Activation Function (tanh)

The project uses:

```text
tanh()
```

as the nonlinear activation function.

Its role is to introduce nonlinear representation capability.

Without nonlinear activation functions, even very deep networks would still behave like linear models and fail to learn complex spiral decision boundaries.

---

## 4. Loss Function

The project uses Mean Squared Error (MSE):

```text
L = 1/2 (y - a)^2
```

to measure prediction error between network output and ground truth labels.

---

## 5. Backpropagation

Backpropagation is implemented completely from scratch.

Its purpose is to compute how each parameter (weights and biases) affects the loss function.

Using the chain rule, gradients are calculated and propagated backward through the network to update parameters automatically.

---

## 6. Stochastic Gradient Descent (SGD)

Parameters are optimized using SGD:

```text
W = W - η * dL/dW
```

The training loop repeatedly performs:

```text
Input Data
→ Feed Forward
→ Compute Loss
→ Backpropagation
→ Update Parameters
```

until the loss converges.

---

# Experiments

## Experiment 1: Simple Binary Classification

The first experiment uses linearly separable datasets:

```text
Blue Blue Blue | Red Red Red
```

to verify:

- Network structure correctness
- Feed Forward correctness
- Backpropagation correctness
- SGD convergence

---

## Experiment 2: Spiral Nonlinear Classification

The second experiment uses the Spiral dataset:

```text
🌀🌀🌀
```

which contains highly nonlinear decision boundaries.

The experiment focuses on studying the representation capability of deep neural networks for complex nonlinear functions.

---

# Why Deep Networks Work Better

Shallow neural networks can only represent relatively simple functions.

As a result, they can only generate simple decision boundaries.

Deep neural networks repeatedly apply:

```text
Linear Transformation
+
Nonlinear Activation
```

which continuously transforms and distorts the input space.

This allows the network to learn highly complex nonlinear functions and generate complicated Spiral decision boundaries.

---

# Decision Boundary Visualization

After training, the neural network has already learned:

```text
F(x,y)
```

The project then samples the entire 2D plane using grid points such as:

```text
100 × 100
```

Each sampled point is passed into the neural network to compute:

```text
F(x,y)
```

Where:

- Positive values belong to the red region
- Negative values belong to the blue region

MATLAB/Octave then searches for locations where:

```text
F(x,y)=0
```

and connects these locations to generate the final decision boundary visualization.

---

# Project Highlights

- Implemented a neural network training system completely from scratch
- No TensorFlow or PyTorch used
- Deep understanding of Backpropagation and neural network mathematics
- Studied how deep neural networks learn nonlinear functions
- Successfully implemented nonlinear Spiral classification
- Visualized complex decision boundaries

---

# Tech Stack

- C++
- Neural Networks
- Backpropagation
- SGD Optimization
- Numerical Optimization
- MATLAB / Octave
- Matrix Computation

---

# Results

- Successfully completed binary classification tasks
- Learned complex nonlinear Spiral decision boundaries
- Demonstrated stronger representation capability of deep neural networks
- Completed full neural network training and visualization pipeline
