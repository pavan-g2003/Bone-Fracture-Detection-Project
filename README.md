# Bone-Fracture-Detection-Project
# Bone Fracture Detection and Classification using U-Net and Dual-Attention Swin Transformer

## Overview

Bone fractures are among the most common musculoskeletal injuries and require accurate diagnosis for effective treatment. Manual interpretation of X-ray images can be time-consuming and may vary depending on the radiologist's expertise.

This project presents an end-to-end deep learning framework for automatic bone fracture detection and classification from X-ray images. The proposed pipeline integrates image preprocessing, semantic segmentation, region-of-interest extraction, transformer-based classification, and explainable AI to improve diagnostic accuracy and interpretability.

---

## Features

- Image preprocessing using CLAHE
- Bone segmentation using U-Net
- ROI extraction
- Dual-Attention Swin Transformer classifier
- Grad-CAM visualization
- Confusion Matrix
- Accuracy, Precision, Recall and F1-score evaluation
- End-to-end medical image analysis pipeline

---

## Dataset

**Dataset Source**

Kaggle:
Bone Fracture Detection Computer Vision Project

Dataset contains X-ray images belonging to seven anatomical categories:

- Elbow
- Fingers
- Forearm
- Humerus
- Humerus Fracture
- Shoulder
- Wrist

---

## Project Pipeline

```
Bone Fracture X-ray Images
            │
            ▼
Image Preprocessing
(Resize + CLAHE)
            │
            ▼
Bone Segmentation
(U-Net)
            │
            ▼
ROI Extraction
            │
            ▼
Dual-Attention
Swin Transformer
            │
            ▼
Classification
            │
            ▼
Evaluation
            │
            ▼
Grad-CAM Explainability
```

---

## Image Preprocessing

Medical X-ray images usually contain

- Low contrast
- Uneven illumination
- Noise
- Background artifacts

To improve image quality, the following preprocessing techniques were applied:

### Image Resizing

All images were resized to a fixed input size before training.

### CLAHE (Contrast Limited Adaptive Histogram Equalization)

CLAHE improves local contrast while preventing excessive noise amplification.

Advantages:

- Enhances fracture visibility
- Preserves bone edges
- Improves local contrast
- Produces better feature representation

---

## Bone Segmentation

Instead of classifying the entire X-ray image directly, a U-Net model was used to segment the bone region.

Why U-Net?

- Designed specifically for biomedical image segmentation
- Skip connections preserve anatomical details
- Excellent performance on small medical datasets
- Removes unnecessary background information

The output segmentation mask is later used to extract the Region of Interest (ROI).

---

## ROI Extraction

The segmented bone mask is used to extract only the important anatomical region.

Benefits:

- Removes irrelevant background
- Reduces computational complexity
- Improves classifier performance
- Forces the model to focus on fracture regions

---

## Classification

A Dual-Attention Swin Transformer was implemented for fracture classification.

### Swin Transformer

The Swin Transformer captures both local and global image features using hierarchical shifted-window self-attention.

Advantages:

- Learns long-range dependencies
- Better contextual understanding
- More efficient than standard Vision Transformers
- Suitable for high-resolution medical images

### Channel Attention

Learns which feature channels are more informative.

### Spatial Attention

Learns where the fracture is located within the image.

Combining both attention mechanisms allows the network to focus on clinically relevant fracture regions.

---

## Explainable AI

To improve model transparency, Grad-CAM was integrated.

Grad-CAM generates heatmaps highlighting image regions responsible for the model prediction.

Benefits:

- Improves interpretability
- Builds clinician trust
- Verifies model attention
- Supports explainable diagnosis

---

## Performance Evaluation

Model performance was evaluated using:

- Accuracy
- Precision
- Recall
- F1-score
- Confusion Matrix

---

## Technologies Used

- Python
- PyTorch
- OpenCV
- NumPy
- Matplotlib
- Albumentations
- Torchvision
- Scikit-learn

---



## Installation

Clone the repository

```bash
git clone https://github.com/yourusername/Bone-Fracture-Detection.git
```

Move into the project directory

```bash
cd Bone-Fracture-Detection
```

Install dependencies

```bash
pip install -r requirements.txt
```

Run the notebook

```bash
jupyter notebook
```

or

Open the notebook directly in Google Colab.

---

## Results

The proposed framework successfully performs

- Bone segmentation
- ROI extraction
- Fracture classification
- Model explainability

The combination of U-Net, Dual-Attention Swin Transformer and Grad-CAM improves both classification performance and interpretability, making the framework suitable for biomedical imaging applications.

---

## Future Work

Future improvements include:

- Multi-label fracture detection
- Fracture localization
- Integration with Vision Foundation Models
- Lightweight deployment for edge devices
- Clinical validation on larger datasets

---

## Author

**Pavan G**

MCA (Artificial Intelligence & Data Science)

Interested in Computer Vision, Deep Learning, Biomedical Imaging and Explainable AI.
