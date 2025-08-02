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

| Epoch 0 | Epoch 5 | Epoch 15 |
|---------|---------|----------|
| ![Epoch 0](images/epoch0.png) | ![Epoch 5](images/epoch5.png) | ![Epoch 15](images/epoch15.png) |

---

##  Key Challenges & Solutions

| Challenge | Solution |
|----------|-----------|
| Training Instability | Used SGD with momentum + tuned learning rate |
| Mode Collapse | Proposed architecture changes and data augmentation |
| Vanishing Gradients | Avoided BatchNorm in Discriminator |
| Hyperparameter Sensitivity | Careful tuning of learning rate, batch size |

---

##  Future Improvements

- Replace DCGAN with more advanced blocks (e.g., ResNet-based GANs)
- Introduce **conditional generation** (e.g., generate a specific digit)
- Add **learning rate scheduling** for dynamic adaptation
- Augment training data with transformations to increase generalization

---

## 📁 Project Structure


