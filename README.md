# 🌊 Marine Species Classification using Deep Learning

## 📌 Overview

This project implements a complete deep learning pipeline for **marine species classification** using underwater imagery from the **FathomNet dataset**. The goal is to design, train, and evaluate both a **custom Convolutional Neural Network (CNN)** and a **transfer learning model**, while also handling **out-of-distribution (OOD) detection**.

---

## 🎯 Objectives

* Build a CNN model from scratch for multi-class classification
* Apply transfer learning using a pretrained backbone (MobileNetV2)
* Compare different training strategies
* Implement a simple OOD detection mechanism
* Evaluate models using comprehensive metrics

---

## 📂 Dataset

* Source: [FathomNet](https://www.fathomnet.org/)
* ~2400 underwater images
* Multiple marine species classes
* Balanced dataset (equal samples per class)

---

## ⚙️ Project Pipeline

### 1️⃣ Data Preparation

* Retrieved data using FathomNet API
* Downloaded and stored images locally
* Preprocessed images:

  * Resizing to 224×224
  * Normalization
* Created:

  * Training set (80%)
  * Validation set (20%)
  * OOD set (unseen classes)

---

### 2️⃣ Model A — CNN from Scratch

* Architecture:

  * 3 Convolutional Blocks (Conv → ReLU → MaxPool)
  * Fully connected classification head
* Regularization:

  * Dropout
* Training:

  * Multiple configurations (different learning rates)

---

### 3️⃣ Model B — Transfer Learning

* Backbone: **MobileNetV2 (ImageNet pretrained)**

Implemented 3 strategies:

* **Feature Extraction** → frozen backbone
* **Partial Fine-Tuning** → unfreeze top layers
* **Full Fine-Tuning** → train entire model

---

### 4️⃣ OOD Detection

* Used softmax confidence threshold
* If prediction confidence < threshold → classified as **unknown**
* Evaluated using:

  * Precision
  * Recall

---

### 5️⃣ Evaluation Metrics

* Accuracy
* Precision, Recall, F1-score (per class)
* Macro F1-score
* Confusion Matrix
* Training & Validation curves

---

## 📊 Results

* CNN Model Accuracy: ~81%
* Transfer Learning Accuracy: ~83%
* Macro F1 Score: ~0.81
* OOD Detection:

  * High recall for detecting unknown samples
  * Moderate precision (threshold-dependent)

---

## 🛠️ Technologies Used

* Python
* TensorFlow / Keras
* NumPy, Pandas
* Scikit-learn
* Matplotlib

---

## ▶️ How to Run

1. Install dependencies:

```bash
pip install -r requirements.txt
```

2. Run the notebook:

```bash
jupyter notebook
```

3. Execute all cells to:

* Download dataset
* Train models
* Evaluate results

---

## 🔁 Reproducibility

* Random seeds fixed for NumPy and TensorFlow
* Requirements file included
* Full pipeline runs from start to finish

---

## 🚀 Future Improvements

* Apply advanced data augmentation
* Use more powerful architectures (EfficientNet, ResNet)
* Improve OOD detection (e.g., temperature scaling, entropy-based methods)
* Hyperparameter optimization

---

## 👨‍💻 Author

**Abdelhady Mohamed**
Communication and Information Engineering Student | Deep Learning & Computer Vision Enthusiast

---
