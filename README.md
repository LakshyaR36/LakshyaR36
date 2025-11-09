# 🛰️ Satellite Imagery Semantic Segmentation using U-Net  

![Python](https://img.shields.io/badge/Python-3.10-blue?logo=python)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.15-orange?logo=tensorflow)
![Keras](https://img.shields.io/badge/Keras-Deep%20Learning-red?logo=keras)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Active-success)

> 🌍 **Automated Land Cover Classification** using deep learning on satellite images — transforming pixels into powerful insights for urban planning, environment monitoring, and GIS applications.

---

## 📖 Project Overview  

This project demonstrates **semantic segmentation** of high-resolution **satellite imagery** using a **Lite U-Net architecture**.  
The model classifies each pixel in a satellite image into land cover categories such as:

- 🏢 **Buildings**  
- 🌳 **Vegetation**  
- 🚗 **Roads**  
- 💧 **Water Bodies**  
- 🏜️ **Barren Land**  
- ⛰️ **Other Surfaces**

The U-Net model has been carefully optimized for lightweight training while preserving segmentation accuracy, achieving **~89.6% training accuracy** and **~78.8% validation accuracy** on test data.

---

## 🧠 Problem Statement  

Manual analysis of satellite imagery is **slow, subjective, and expensive**.  
Traditional classification methods fail to identify fine-grained spatial details like roads, rivers, or small buildings.  
The goal of this project is to build a **deep learning-based pixel-wise classifier** to automatically segment land cover regions, enabling scalable environmental analysis.

---

## ⚙️ Model Architecture — Lite U-Net  

The model follows an **encoder–decoder** structure:  


✨ **Key Highlights:**
- Dropout Regularization (0.2)
- Adam Optimizer (`lr=1e-4`)
- Sparse Categorical Crossentropy Loss
- Skip connections for spatial feature preservation
- 6 Output Classes (Softmax Activation)

---

## 🧩 Dataset & Preprocessing  

| Step | Description |
|------|--------------|
| **Source** | High-resolution satellite imagery dataset (6 classes) |
| **Resolution** | Resized to 128×128 pixels |
| **Normalization** | Scaled pixel values to [0, 1] |
| **Augmentation** | Random flips, rotations, brightness variation |
| **Split** | 80% training / 20% validation |

💡 **Challenges:** Class imbalance, illumination variation, small-scale features (roads/buildings).

---

## 🚀 Training Details  

| Parameter | Value |
|------------|--------|
| **Epochs** | 150 |
| **Batch Size** | 1 |
| **Optimizer** | Adam |
| **Learning Rate** | 1e-4 |
| **Loss Function** | Sparse Categorical Crossentropy |
| **Metric** | Accuracy |

**Callbacks Used:**
- ✅ `ModelCheckpoint` — saves best model  
- ⏹️ `EarlyStopping` — halts training to prevent overfitting  

---

## 📈 Results & Visualization  

| Metric | Train | Validation |
|---------|--------|------------|
| **Accuracy** | 0.8966 | 0.7881 |
| **Loss** | 0.2858 | 0.7070 |


