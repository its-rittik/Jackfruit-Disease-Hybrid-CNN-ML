# Feature-Optimized Hybrid CNN-ML Architecture for Robust Jackfruit Disease Classification

This repository contains the official implementation for the research paper: 
**"Feature-Optimized Hybrid CNN-ML Architecture for Robust Jackfruit Disease Classification in Resource-Constrained Settings."**

---

## 📖 Research Overview
This study addresses the challenges of automated plant disease detection in tropical regions where environmental variability and limited computational resources are significant barriers. 

We propose a **hybrid Deep Learning-Machine Learning (DL-ML)** framework that:
* Extracts deep visual representations using a **lightweight custom CNN** and a **pre-trained ResNet50**.
* Bridges the performance-efficiency gap using **Principal Component Analysis (PCA)** and **SMOTE**.
* Classifies diseases using a high-performance **stacked ensemble model**.



---

## 🛠️ Project Structure & Methodology
The research follows a 7-stage progressive methodology to transition from raw baseline models to the final optimized hybrid architecture.

| Stage | Methodology | Repository Notebook | Accuracy |
| :--- | :--- | :--- | :--- |
| 1 | Raw ML Baseline (RF, SVM, etc.) | `direct_ml_and_dl.ipynb` | 76.80% |
| 2 | Custom CNN Feature Extraction | `without_augment_custom_cnn.ipynb` | 79.75% |
| 3 | SMOTE + PCA Feature Balancing | `pca_smote.ipynb` | 90.74% |
| 4 | DL Extraction (ResNet50) | `feature_extraction.ipynb` | 90.20% |
| 5 | DL + SMOTE/PCA Refinement | `pca_smote.ipynb` | 96.71% |
| 6 | Augmented ML (9,000 images) | `data_augmentation.ipynb` | 95.39% |
| **7** | **Final Hybrid: Custom CNN + PCA** | `with_augment_custom_cnn.ipynb` | **99.39%** |

---

## 📂 Dataset Details
* **Original Data:** 2,195 images collected from Barishal and Khulna, Bangladesh.
* **Expanded Data:** 9,000 images after data augmentation (rotation, flipping, brightness).
* **Classes:** Fruit Damage, Rhizopus Rot, Healthy Jackfruit, Leaf Blight, Leaf Spot, and Healthy Leaf.
* **Quality Control:** Validated via **PSNR** (min 24dB), **SSIM** (0.86-0.95), and **MS-SSIM** (0.976-0.982).



---

## 📈 Ensemble Model & Ablation Study
We implemented a 5-stage ensemble learning pipeline featuring temperature scaling and meta-model stacking:
* **V1:** Preliminary Stacking.
* **V2:** Weighted Probability Blending.
* **V3:** Calibrated Meta-Learner Fusion.
* **V4 (Final):** **Adaptive Temperature Calibration + Weighted Blending.**

---

## 🚀 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/its-rittik/Jackfruit-Disease-Hybrid-CNN-ML.git](https://github.com/its-rittik/Jackfruit-Disease-Hybrid-CNN-ML.git)
   cd Jackfruit-Disease-Hybrid-CNN-ML
