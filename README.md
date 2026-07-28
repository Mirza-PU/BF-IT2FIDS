# BF-IT2FIDS: Bipolar Fuzzy Interval Type-2 Fuzzy Intrusion Detection System

<p align="center">

<h2 align="center">
BF-IT2FIDS: A Bipolar Fuzzy–Interval Type-2 Hybrid Framework for Robust Intrusion Detection in Edge-IIoT Applications
</h2>

<p align="center">
Official PyTorch Implementation
</p>

<p align="center">

![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![PyTorch](https://img.shields.io/badge/PyTorch-2.0+-EE4C2C.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)
![Research](https://img.shields.io/badge/Research-Deep%20Learning-success.svg)
![Platform](https://img.shields.io/badge/Platform-Linux%20%7C%20Windows%20%7C%20Kaggle-green.svg)

</p>

---

## 📖 Overview

BF-IT2FIDS (**Bipolar Fuzzy Interval Type-2 Fuzzy Intrusion Detection System**) is a novel deep learning framework designed for robust multiclass intrusion detection in **Industrial Internet of Things (IIoT)** environments.

The proposed framework integrates **Bipolar Fuzzy Logic**, **Interval Type-2 Fuzzy Feature Engineering**, and a **regularized Multi-Layer Perceptron (MLP)** to effectively capture uncertainty, nonlinear relationships, and ambiguity in network traffic before classification.

Unlike conventional intrusion detection systems that directly process raw features, BF-IT2FIDS expands every feature into multiple uncertainty-aware fuzzy representations, significantly improving robustness and generalization.

---

## ✨ Key Contributions

- Novel Bipolar Interval Type-2 Fuzzy feature engineering.
- Uncertainty-aware feature transformation.
- Deep regularized Multi-Layer Perceptron.
- Batch Normalization and Dropout.
- AdamW optimization.
- Cosine Annealing learning rate scheduling.
- Class-weighted Cross-Entropy Loss.
- Gradient Clipping.
- Early Stopping.
- Multi-seed reproducibility.
- Publication-quality evaluation.

---

# 🏗 BF-IT2FIDS Pipeline

```
Raw Edge-IIoT Dataset
          │
          ▼
──────────────────────────────
Data Cleaning
• Missing Values
• Encoding
──────────────────────────────
          │
          ▼
RobustScaler
          │
          ▼
──────────────────────────────
Bipolar Interval Type-2
Fuzzy Feature Engineering

Lower Membership

Upper Membership

Positive Membership

Negative Membership

Expanded Features = 4 × Original Features
──────────────────────────────
          │
          ▼
Deep Regularized MLP

Input
 │
512
 │
BatchNorm
 │
ReLU
 │
Dropout (0.4)
 │
256
 │
BatchNorm
 │
ReLU
 │
Dropout (0.3)
 │
128
 │
ReLU
 │
Output Layer
 │
Softmax
          │
          ▼
Attack Prediction
```

---

# 🚀 Features

✅ Interval Type-2 Fuzzy Feature Expansion

✅ Bipolar Fuzzy Representation

✅ Deep Multi-Layer Perceptron

✅ RobustScaler Normalization

✅ Batch Normalization

✅ Dropout Regularization

✅ AdamW Optimizer

✅ Cosine Annealing Scheduler

✅ Early Stopping

✅ Gradient Clipping

✅ Class Weighted Loss

✅ Multi-Class Intrusion Detection

---

# 🧠 Network Architecture

| Layer | Configuration |
|---------|--------------|
| Input | 4 × Original Features |
| Hidden Layer 1 | Linear (512) |
| BatchNorm | ✓ |
| ReLU | ✓ |
| Dropout | 0.40 |
| Hidden Layer 2 | Linear (256) |
| BatchNorm | ✓ |
| ReLU | ✓ |
| Dropout | 0.30 |
| Hidden Layer 3 | Linear (128) |
| ReLU | ✓ |
| Output Layer | Number of Classes |
| Activation | Softmax |

---

# ⚙ Hyperparameters

| Component | Value |
|------------|-------|
| Scaler | RobustScaler |
| Missing Values | Filled with Zero |
| Lower Gaussian | 0.7 |
| Upper Gaussian | 0.3 |
| Optimizer | AdamW |
| Learning Rate | 0.001 |
| Weight Decay | 1e-4 |
| Scheduler | CosineAnnealingLR |
| Epochs | 100 |
| Batch Size | 4096 |
| Early Stopping | Patience = 10 |
| Gradient Clipping | 1.0 |
| Loss Function | Class Weighted CrossEntropy |

---

# 📊 Dataset

This framework is evaluated on the **Edge-IIoTset** benchmark dataset.

Dataset Characteristics

- Industrial IoT Traffic
- 15 Attack Classes
- Multiclass Classification
- Large-scale Network Flows

---

# 📂 Repository Structure

```text
BF-IT2FIDS/
│
├── data/
│   ├── preprocessing.py
│   └── dataset_loader.py
│
├── models/
│   ├── bf_it2fids.py
│   ├── fuzzy_layer.py
│   └── mlp.py
│
├── utils/
│   ├── metrics.py
│   ├── visualization.py
│   ├── preprocessing.py
│   └── seed.py
│
├── outputs/
│   ├── confusion_matrix.png
│   ├── learning_curve.png
│   ├── results.csv
│   └── logs/
│
├── main.py
├── requirements.txt
├── LICENSE
└── README.md
```

---

# 💻 Installation

Clone the repository

```bash
git clone https://github.com/Mirza-PU/BF-IT2FIDS.git

cd BF-IT2FIDS
```

Install dependencies

```bash
pip install -r requirements.txt
```

---

# ▶️ Usage

Train the model

```bash
python main.py
```

The framework automatically performs

- Data preprocessing
- Feature scaling
- Bipolar fuzzy transformation
- Model training
- Validation
- Testing
- Performance evaluation
- Learning curve generation
- Confusion matrix generation
- Risk score estimation

---

# 📈 Experimental Results

The proposed BF-IT2FIDS achieves outstanding multiclass intrusion detection performance.

| Metric | Score |
|---------|-------|
| Accuracy | **99.75%** |
| Precision | **99.75%** |
| Recall | **99.75%** |
| Macro F1-score | **99.75%** |

---
