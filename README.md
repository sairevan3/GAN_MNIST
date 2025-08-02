# GAN-MNIST: Image Generation using Deep Convolutional GAN

This project implements a Deep Convolutional Generative Adversarial Network (DCGAN) using Keras and OpenCV to generate **realistic 28×28 MNIST digit images** from 100-dimensional random noise. It focuses on stable adversarial training dynamics, visual output inspection, and model quality evaluation using **Fréchet Inception Distance (FID)**.

---

##  Objectives

- Build a functional GAN to generate synthetic images from the MNIST dataset.
- Stabilize training between Generator and Discriminator.
- Evaluate model quality using visual inspection and FID score.

---

##  Tech Stack

- **Python**
- **Keras (TensorFlow backend)**
- **OpenCV**
- **NumPy**
- **Matplotlib**

---

##  Model Architecture

### Generator
- Input: 100-dimensional random noise vector
- Layers: Dense → Batch Normalization → UpSampling → Conv2D
- Output: 28x28 grayscale image

### Discriminator
- Input: 28x28 grayscale image
- Layers: Conv2D → MaxPooling → Dense
- Output: Binary classification (real or fake)

> Batch Normalization is used **only in the Generator** to prevent overfitting and help stable training.

---

##  Training Details

| Parameter | Value |
|-----------|-------|
| Optimizer | SGD with Momentum (0.9) + Nesterov |
| Loss Function | Binary Cross-Entropy |
| Batch Size | 128 |
| Learning Rate | 0.0005 |
| Dataset | MNIST (70,000 total images, grayscale 28x28) |

---

##  Evaluation

- **Fréchet Inception Distance (FID):** 16.80  
- **Visual Inspection:** Realism and diversity improve significantly after 15 epochs.

### Epoch-wise Samples:

| Epoch 0 | Epoch 5 | Epoch 15 | Epoch 50 |
|---------|---------|----------|----------|
| ![Epoch 0](https://github.com/user-attachments/assets/c0d17fd7-9753-4bbc-97b1-f0e262611e1c) | ![Epoch 5](https://github.com/user-attachments/assets/0dbd1bcb-5167-42ec-9144-8be5b6f213b5) | ![Epoch 15](https://github.com/user-attachments/assets/dd2d9f25-4afb-4d61-b18c-d88d36269660) | ![Epoch 50](https://github.com/user-attachments/assets/be836f3f-9eaa-447f-aba7-7f756aa968ed) |

---


