# 🐶 Cat vs. Dog Image Classifier 🐱

![TensorFlow](https://img.shields.io/badge/TensorFlow-%23FF6F00.svg?style=for-the-badge&logo=TensorFlow&logoColor=white)
![Keras](https://img.shields.io/badge/Keras-%23D00000.svg?style=for-the-badge&logo=Keras&logoColor=white)
![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Status](https://img.shields.io/badge/Status-Completed-success)

A Deep Learning project that classifies images of Cats and Dogs using a Convolutional Neural Network (CNN). This project demonstrates the end-to-end pipeline of loading a large dataset, cleaning corrupt data, building a custom CNN architecture, and mitigating overfitting.

## 📌 Project Overview

This model takes an input image and predicts whether it contains a **Cat** or a **Dog**. It was trained on the **Microsoft PetImages dataset** (approx. 25,000 images).

**Key Achievements:**
* Built a custom CNN architecture from scratch.
* Implemented automated data cleaning to handle corrupt/empty files in the dataset.
* Achieved **~82% accuracy** on unseen validation data.
* Utilized **Batch Normalization** and **Dropout** to stabilize training.

## 📂 Dataset

The project uses the publicly available Microsoft PetImages dataset (often found on Kaggle).

* **Classes:** 2 (Cat, Dog)
* **Total Images:** ~25,000
* **Preprocessing:**
    * Resized to `(256, 256)`
    * Normalized pixel values (rescaling 0-255).
    * Split: 80% Training, 20% Validation.

> **⚠️ Data Challenge:** The raw dataset contains several corrupt files (zero-byte files and non-standard headers). A custom cleaning script was implemented to verify and remove these files before training to prevent `InvalidArgumentError`.

## 🏗️ Model Architecture

The model is built using `tensorflow.keras.Sequential` with the following structure:

1.  **Convolutional Layers:** Extract features (edges, textures, shapes).
2.  **Batch Normalization:** Applied to normalize layer inputs and speed up training.
3.  **MaxPooling:** Reduces spatial dimensions.
4.  **Dropout:** Randomly ignores neurons during training to prevent overfitting.
5.  **Dense Layers:** Fully connected layers for final classification.
6.  **Output Layer:** Sigmoid activation (for binary classification).

## 📊 Performance & Results

The model was trained for 10 epochs.

| Metric | Training Score | Validation Score |
| :--- | :--- | :--- |
| **Accuracy** | ~96.8% | **~82.0%** |
| **Loss** | 0.08 | 0.41 (Best) |

### Observations
* **Overfitting:** Around Epoch 5, the model began to overfit (Training accuracy continued to rise to 98%, while Validation loss increased).
* **Solution:** Techniques like Dropout and Batch Normalization were added. Future improvements could include **Data Augmentation** (rotation, zoom) and **Early Stopping** to capture the model at its peak performance (Epoch 5).

## 🚀 How to Run

### Prerequisites
* Python 3.x
* TensorFlow / Keras
* Matplotlib
* Numpy

### Installation
1. Clone the repo:
   ```bash
   git clone [https://github.com/Hanifullah313/Cat_VS_Dog_CNN.git](https://github.com/Hanifullah313/Cat_VS_Dog_CNN.git)
