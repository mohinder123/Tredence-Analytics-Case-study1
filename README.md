# Tredence Analytics Case Study – Self-Pruning Neural Network

Designed and implemented a self-pruning neural network that learns to eliminate redundant weights during training using learnable gating and L1 regularization.

---

## Overview

This project builds a neural network that can automatically identify and suppress unnecessary connections while training.

Instead of pruning after training, the model learns which weights are important using learnable gates.

---

## Key Idea

Each weight has a gate:

W' = W * sigmoid(gate_scores)

* Gate close to 0 → weight removed
* Gate close to 1 → weight kept

---

## Results

### Soft Sparsity

| Lambda | Accuracy | Sparsity |
| ------ | -------- | -------- |
| 0.1    | 46.36%   | 10.76%   |
| 0.5    | 43.74%   | 58.11%   |
| 1.0    | 44.43%   | 61.39%   |

---

### Hard Pruning

| Lambda | Accuracy | Pruned |
| ------ | -------- | ------ |
| 0.1    | 45.28%   | 10.30% |
| 0.5    | 43.90%   | 59.21% |
| 1.0    | 44.12%   | 55.95% |

---

## Observations

* Increasing λ increases sparsity
* Accuracy remains stable even after heavy pruning
* Many weights in the network are redundant
* Proper threshold selection is important for hard pruning

---

## Tech Stack

* Python
* PyTorch
* CIFAR-10
* Matplotlib

---

## Author

Mohinder Singh

