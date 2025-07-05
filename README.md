# 🪐 Mars Terrain Image Segmentation

> Image segmentation of Mars surface images using advanced U-Net-based architectures.  
> **Course:** Artificial Neural Networks and Deep Learning  
> **Team:** Per un pugno di neuroni | Giorgio Algisi, Simone Bresciani, Ilaria Campestrini, Federico Dagani

---

## 📂 Project Overview

This project addresses an **image segmentation task** to detect 5 terrain classes in Mars grayscale images using deep learning.

### ⚠️ Problem Statement

- **Task:** Segmentation of 64x128 grayscale images into 5 classes:
  - Background (excluded in evaluation), Soil, Bedrock, Sand, Big Rock
- **Dataset:**
  - **Training set:** 2615 image-mask pairs
  - **Test set:** 10022 images
- **Challenges:**
  - **Severe class imbalance**, especially for Big Rock (1/154 ratio)
  - Poor quality masks with rough, inaccurate labels
  - Background class exclusion from evaluation metrics

---

## 🔍 Data Preparation

- **Outlier removal:**
  - Detected 110 alien-face outliers using label hash comparison (hash-based image approach failed due to alien variability)
- **Preprocessing:**
  - Normalisation to [0,1]
  - **Data augmentation:** Horizontal flips only (other geometric or brightness augmentations reduced performance)
- **Class imbalance handling:**
  - Calculated class weights based on distribution  
  - Reduced Big Rock weight from ~154 to **10** to avoid over-prediction bias

---

## 🏗️ Model Development

### ✅ Architectural Experiments

| Model           | Validation Mean IoU | Kaggle Score |
|-----------------|---------------------|--------------|
| Simple U-Net    | 51.85 ± 0.6         | 52.45 ± 0.4  |
| Dense U-Net     | 68.60 ± 0.9         | 70.02 ± 0.2  |
| Dual U-Net      | 60.64 ± 1.0         | 58.20 ± 0.5  |
| Parallel U-Net  | 62.65 ± 0.3         | 61.13 ± 0.7  |
| U-Net 3+        | 64.23 ± 0.2         | 65.79 ± 0.1  |
| ResNet++        | 59.59 ± 0.4         | 58.95 ± 0.2  |

- **Key strategies explored:**
  - Dense skip connections (significant performance boost)
  - Dual and Parallel U-Net architectures for multi-scale feature extraction
  - Bottleneck enhancements:
    - **Transformer block** (for global context)  
    - **ASPP (Atrous Spatial Pyramid Pooling)** for multi-scale receptive fields

---

### 🔧 Final Model

- **Architecture:**
  - **Single U-Net with Dense skip connections**
  - Encoder: 4 layers (32, 64, 128, 256 filters)
  - Bottleneck: 512 filters with **Transformer + ASPP block**
  - Decoder: 4 layers mirroring encoder
- **Loss function:**
  - Customized Sparse Categorical Crossentropy with class weights (Background excluded from computation)
- **Training:**
  - **Learning rate scheduler:** ReduceLROnPlateau (LR reduced by factor 0.1 if Mean IoU didn’t improve for 40 epochs)
  - **Early stopping:** Patience=50 (validation loss monitored)
  - Initial LR=1e-3

---

## 📊 Results

- **Final Kaggle score:** **70.633**
- **Observations:**
  - Simpler architectures outperformed complex SotA models designed for medical segmentation tasks
  - Mars terrain problem required **pattern recognition** rather than fine boundary detection

---

## 💡 Future Work

- Explore **CosineDecayRestarts** learning rate scheduler to avoid local minima  
- Develop and test **dynamic loss functions** combining Crossentropy, Dice, and Boundary losses

---

## 🚀 Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/mars-segmentation.git
   cd mars-segmentation
