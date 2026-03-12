# Comparing-pre-trained-CNNs-and-Transformer-for-Knee-Osteoarthritis-Severity-Detection-
Comparing MobileNetV3, InceptionV3, and ViT-B/16 Architectures for KOA classification.
<p align="center">
  <img src="banner.png" width="100%">
</p>

## Overview

This project investigates the performance of modern deep learning architectures for **automated Knee Osteoarthritis (KOA) severity classification** from X-ray images.

We benchmark **Convolutional Neural Networks (CNNs)** and **Vision Transformers (ViTs)** to analyze their representational capabilities in medical imaging tasks.

The study evaluates multiple architectures including:

- InceptionV3
- MobileNetV3Large
- Vision Transformer (ViT-B16)

The goal is to explore how **CNN and transformer-based architectures perform in medical image classification for multi-class severity grading**.

This work is associated with our research presented at **IEEE ICRITO 2025**.

---

## Dataset

Knee X-ray images were organized into **five severity categories**:

| Label | Class |
|-----|------|
| 0 | Normal |
| 1 | Doubtful |
| 2 | Mild |
| 3 | Moderate |
| 4 | Severe |

Dataset split:

| Split | Samples |
|------|--------|
| Train | 1149 |
| Validation | 333 |
| Test | 168 |

Images were resized depending on model architecture.

---

## Model Architectures

### 1️⃣ InceptionV3

Transfer learning using pretrained **ImageNet weights**.

Architecture:


Input Image (299x299)
↓
InceptionV3 (Frozen Backbone)
↓
GlobalAveragePooling
↓
Dense (256, ReLU)
↓
Dropout (0.3)
↓
Softmax (5 classes)


Performance (Test Set):

| Metric | Score |
|------|------|
Accuracy | **0.76**

AUROC:

| Class | AUROC |
|------|------|
Normal | 0.9614 |
Doubtful | 0.8988 |
Mild | 0.9036 |
Moderate | 0.9925 |
Severe | 0.9854 |

---

### 2️⃣ MobileNetV3Large

A lightweight CNN optimized for efficiency and performance.

Architecture:


Input Image (224x224)
↓
MobileNetV3Large Backbone
↓
GlobalAveragePooling
↓
Dense (256, ReLU)
↓
Dropout
↓
Softmax (5 classes)


Performance:

| Metric | Score |
|------|------|
Accuracy | **0.80**

AUROC:

| Class | AUROC |
|------|------|
Normal | 0.9738 |
Doubtful | 0.9250 |
Mild | 0.9317 |
Moderate | 0.9910 |
Severe | 0.9819 |

---

### 3️⃣ Vision Transformer (ViT-B16)

Transformer-based architecture leveraging **global attention mechanisms** for image representation.

Architecture:


Input Image (224x224)
↓
Vision Transformer (ViT-B16 Feature Extractor)
↓
Dense (128, ReLU)
↓
Dropout
↓
Softmax (5 classes)


Performance:

| Metric | Score |
|------|------|
Accuracy | **0.78**

AUROC:

| Class | AUROC |
|------|------|
Normal | 0.9629 |
Doubtful | 0.9234 |
Mild | 0.9271 |
Moderate | 0.9892 |
Severe | 0.9686 |

---

## Evaluation Metrics

Models were evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Specificity
- AUROC
- AUPRC
- Confusion Matrix

Example classification report (MobileNetV3):


Accuracy: 0.80
Macro Avg F1-score: 0.78
Weighted Avg F1-score: 0.79


---

## Training Configuration

| Parameter | Value |
|----------|------|
Batch Size | 32 |
Epochs | 30 |
Optimizer | Adam |
Loss | Sparse Categorical Crossentropy |
Framework | TensorFlow / Keras |



---

## Installation

Clone repository:


git clone https://github.com/shubham-kumar-ai/knee-osteoarthritis-detection.git

cd knee-osteoarthritis-detection


Install dependencies:


pip install tensorflow keras tensorflow-hub scikit-learn matplotlib seaborn


---

## Future Work

- Fine-tuning transformer architectures
- Self-supervised learning for medical imaging
- Explainable AI methods (Grad-CAM)
- Multimodal clinical data integration

---

## Citation

If you use this work, please cite:


Comparing Pre-Trained CNNs and Transformers for Knee Osteoarthritis Severity Detection
IEEE ICRITO 2025


---

## Author

**Shubham Kumar**

## Co-Author

**Aanchal Gupta**

AI Researcher | Bioinformatics | Medical AI
 
MSc Bioinformatics
Chandigarh University 

Focus Areas:

- AI for genomics and proteomics
- Deep learning for medical imaging
- Protein language models
- Bioinformatics tool development
