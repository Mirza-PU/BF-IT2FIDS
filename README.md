# BF-IT2FIDS: Bipolar Fuzzy Interval Type-2 Fuzzy Intrusion Detection System

[![Python 3.10+](https://img.shields.io/badge/python-3.10%2B-blue.svg)](https://www.python.org/)
[![PyTorch](https://img.shields.io/badge/PyTorch-2.0%2B-ee4c2c.svg)](https://pytorch.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Official PyTorch implementation of the framework presented in the paper: **"BF-IT2FIDS: A Bipolar Fuzzy -- Interval Type-2 Hybrid Framework for Robust Intrusion Detection in Edge-IIoT Applications"**.

---

## 🚀 Key Features

* **Uncertainty-Aware Feature Expansion:** Integrates bipolar fuzzy soft computing and interval type-2 uncertainty mapping to handle noise and feature vagueness in industrial IoT telemetry.
* **Regularized Deep MLP Architecture:** Features optimized hidden layer topologies ([512, 256, 128]), batch normalization, and dropout layers ($p_1=0.4, p_2=0.3$).
* **Advanced Training Strategy:** Utilizes AdamW optimization ($\beta_1=0.9, \beta_2=0.999$), cosine annealing learning rate scheduling, class-weighted cross-entropy loss, and gradient clipping ($L_2 \le 1.0$).
* **State-of-the-Art Performance:** Achieves **99.75% Accuracy** and a **0.9975 Macro $F_1$-score** across 15 complex attack classes on the Edge-IIoTset benchmark.

---

## 📁 Repository Structure

```text
BF-IT2FIDS/
│
├── data/                  # Dataset directory (Edge-IIoTset preprocessing scripts)
├── models/                # Architecture definitions (BF-IT2F expansion and MLP)
├── utils/                 # Imputation, scaling, and evaluation metric helpers
├── main.py                # Main execution script for training and evaluation
├── requirements.txt       # Required Python packages
└── README.md              # Project documentation
---

## ⚙️ Hyperparameter Configuration

The framework uses the following verified hyperparameter settings:

| Pipeline Component | Hyperparameter Name | Selected Value / Setting |
| :--- | :--- | :--- |
| **Data Preprocessing** | Scaler Type | Robust Scaler (Median / IQR) |
| | Missing Value / Imputation | Median Imputation with $\epsilon = 10^{-6}$ |
| **Fuzzy Feature Expansion** | Lower Gaussian Spread ($\sigma_1^2$) | $0.7$ |
| | Upper Gaussian Spread ($\sigma_2^2$) | $0.3$ |
| | Sigmoidal Scaling Factor ($\alpha_1$) | $1.0$ |
| | Expanded Feature Dimension | $4 \times M$ ($M$ = Original Features) |
| **Deep Neural Network (MLP)** | Hidden Layer Dimensions | $[512, 256, 128]$ |
| | Activation Function | Rectified Linear Unit (ReLU) |
| | Batch Normalization | Applied after Layers 1 and 2 |
| | Dropout Probabilities ($p_1, p_2$) | $p_1 = 0.4$ (Layer 1), $p_2 = 0.3$ (Layer 2) |
| | Optimizer | AdamW ($\beta_1 = 0.9, \beta_2 = 0.999$) |
| | Initial Learning Rate ($\eta_{\max}$) | $0.001$ |
| | Weight Decay ($\lambda$) | $10^{-4}$ |
| **Training Strategy** | Loss Function | Class-Weighted Cross-Entropy |
| | Learning Rate Scheduler | Cosine Annealing |
| | Gradient Clipping Norm ($L_2$) | $\le 1.0$ |

---

## 📥 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/Mirza-PU/BF-IT2FIDS.git](https://github.com/Mirza-PU/BF-IT2FIDS.git)
   cd BF-IT2FIDS
