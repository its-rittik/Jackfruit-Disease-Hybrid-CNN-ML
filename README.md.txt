# Feature-Optimized Hybrid CNN-ML for Jackfruit Disease Classification

[![Status](https://img.shields.io/badge/Status-Under_Review-orange)](#) 
[![Python](https://img.shields.io/badge/Python-3.8+-yellow?logo=python)](https://www.python.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange?logo=tensorflow)](https://tensorflow.org/)

This repository contains the official implementation for the research paper: **"Feature-Optimized Hybrid CNN-ML Architecture for Robust Jackfruit Disease Classification in Resource-Constrained Settings."**

## 📖 Research Overview
[cite_start]This study addresses the challenges of automated plant disease detection in tropical regions where environmental variability and limited computational resources are significant barriers[cite: 11]. [cite_start]We propose a hybrid Deep Learning-Machine Learning (DL-ML) framework that extracts deep visual representations using a lightweight custom CNN and a pre-trained ResNet50[cite: 14, 15]. [cite_start]To bridge the performance-efficiency gap, features are optimized via **Principal Component Analysis (PCA)** and **SMOTE** before being classified by a high-performance stacked ensemble model[cite: 16, 17].

## 🛠️ Project Structure & Methodology
The research follows a 7-stage progressive methodology to transition from raw baseline models to the final optimized hybrid architecture:

| Stage | Methodology | Repository Notebook | Accuracy |
| :--- | :--- | :--- | :--- |
| **1** | [cite_start]**Raw ML Baseline**: Traditional classifiers (RF, SVM, etc.) on raw images[cite: 661]. | `direct_ml_and_dl.ipynb` | [cite_start]76.80% [cite: 668] |
| **2** | [cite_start]**Custom CNN Ext.**: Feature extraction using a lightweight 3-block CNN[cite: 740]. | `without_augment_custom_cnn.ipynb` | [cite_start]79.75% [cite: 749] |
| **3** | [cite_start]**SMOTE + PCA**: Balancing and compressing Custom CNN features[cite: 818]. | `pca_smote.ipynb` | [cite_start]90.74% [cite: 827] |
| **4** | **DL Ext. (ResNet50)[cite_start]**: Deep feature extraction using pre-trained ResNet50[cite: 867]. | `feature_extraction.ipynb` | [cite_start]90.20% [cite: 872] |
| **5** | [cite_start]**DL + SMOTE/PCA**: Optimized ResNet50 features with hybrid refinement[cite: 965]. | `pca_smote.ipynb` | [cite_start]96.71% [cite: 897] |
| **6** | [cite_start]**Augmented ML**: Direct ML on a balanced dataset of 9,000 images[cite: 978]. | `data_augmentation.ipynb` | [cite_start]95.39% [cite: 1020] |
| **7** | [cite_start]**Final Hybrid**: **Custom CNN + PCA on Augmented Data**[cite: 1096]. | `with_augment_custom_cnn.ipynb` | [cite_start]**99.39%** [cite: 1104] |



## 📂 Dataset Details
[cite_start]The primary dataset consists of **2,195 images** collected from Barishal and Khulna, Bangladesh[cite: 252]. [cite_start]Through data augmentation (rotation, flipping, brightness), the set was expanded to **9,000 images** to ensure class balance[cite: 372, 375].

* [cite_start]**Classes**: Fruit Damage, Rhizopus Rot, Healthy Jackfruit, Leaf Blight, Leaf Spot, and Healthy Leaf[cite: 253].
* **Quality Metrics**: Preprocessed images were validated using PSNR (min 24dB), SSIM (0.86-0.95), and MS-SSIM (0.976-0.982)[cite: 380].



## 📈 Ensemble Model & Ablation Study
We implemented a 5-stage ensemble learning pipeline featuring temperature scaling and meta-model stacking[cite: 547]. 
* [cite_start]**V1**: Preliminary Stacking[cite: 1159].
* [cite_start]**V2**: Weighted Probability Blending[cite: 1164].
* **V3**: Calibrated Meta-Learner Fusion[cite: 1167].
* [cite_start]**V4 (Final)**: **Adaptive Temperature Calibration + Weighted Blending**[cite: 1171].



## 🚀 Installation
```bash
git clone [https://github.com/its-rittik/Jackfruit-Disease-Hybrid-CNN-ML.git](https://github.com/its-rittik/Jackfruit-Disease-Hybrid-CNN-ML.git)
pip install -r requirements.txt