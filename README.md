# Neural Network from Scratch (MNIST)

A minimal **two-layer neural network** implemented from first principles to classify handwritten digits from the **MNIST** dataset. The project emphasizes mathematical clarity, correct tensor shapes, and a transparent training loop (forward pass, backpropagation, and parameter updates).

---

## Repository Structure

```
.
├── nn_FROM_sCRATCH.ipynb   # End-to-end notebook (data, training, evaluation)
├── README.md              # Project overview and math
└── assets/                # (optional) figures, plots
```

---

## Model Architecture

Our NN uses a simple two-layer architecture:

* **Input layer** (a^{[0]}): 784 units (flattened (28 \times 28) image)
* **Hidden layer** (a^{[1]}): 10 units with **ReLU** activation
* **Output layer** (a^{[2]}): 10 units with **Softmax** activation (digit classes 0–9)

---

## Forward Propagation

[
Z^{[1]} = W^{[1]} X + b^{[1]}
]
[
A^{[1]} = g_{\text{ReLU}}(Z^{[1]})
]
[
Z^{[2]} = W^{[2]} A^{[1]} + b^{[2]}
]
[
A^{[2]} = g_{\text{softmax}}(Z^{[2]})
]

---

## Backward Propagation

[
dZ^{[2]} = A^{[2]} - Y
]
[
dW^{[2]} = \frac{1}{m} dZ^{[2]} A^{[1]T}
]
[
dB^{[2]} = \frac{1}{m} \sum dZ^{[2]}
]
[
dZ^{[1]} = W^{[2]T} dZ^{[2]} ; .* ; g^{[1]\prime}(Z^{[1]})
]
[
dW^{[1]} = \frac{1}{m} dZ^{[1]} A^{[0]T}
]
[
dB^{[1]} = \frac{1}{m} \sum dZ^{[1]}
]

---

## Parameter Updates (Gradient Descent)

[
W^{[2]} := W^{[2]} - \alpha dW^{[2]}
]
[
b^{[2]} := b^{[2]} - \alpha db^{[2]}
]
[
W^{[1]} := W^{[1]} - \alpha dW^{[1]}
]
[
b^{[1]} := b^{[1]} - \alpha db^{[1]}
]

---

## Variables and Tensor Shapes

### Forward Propagation

* (A^{[0]} = X): (784 \times m)
* (W^{[1]}): (10 \times 784)
* (B^{[1]}): (10 \times 1)
* (Z^{[1]}, A^{[1]}): (10 \times m)
* (W^{[2]}): (10 \times 10)
* (B^{[2]}): (10 \times 1)
* (Z^{[2]}, A^{[2]}): (10 \times m)

### Backpropagation

* (dZ^{[2]}): (10 \times m)
* (dW^{[2]}): (10 \times 10)
* (dB^{[2]}): (10 \times 1)
* (dZ^{[1]}): (10 \times m)
* (dW^{[1]}): (10 \times 784)
* (dB^{[1]}): (10 \times 1)

---

## Loss Function

* **Categorical Cross-Entropy** with Softmax output

---

## How to Run

1. Open `neural_network_frm_scratch `
2. Run all cells sequentially
3. Observe training loss and accuracy on MNIST

---

## Design Notes

* Vectorized NumPy implementation (no deep learning frameworks)
* Explicit shape tracking for correctness
* Suitable for academic understanding and interview preparation

---

## References (Suggested Reading)

* *Deep Learning* — Ian Goodfellow, Yoshua Bengio, Aaron Courville
* *Neural Networks and Learning Machines* — Simon Haykin
* CS231n Lecture Notes (Stanford)
* Andrew Ng, *Neural Networks and Deep Learning*

---

## License

MIT License

