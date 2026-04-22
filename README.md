# 🧪 Pill Anomaly Detection  
**Feature-based vs Deep Learning Approaches for Visual Inspection**

---

## 📌 Overview

This project explores anomaly detection in pharmaceutical pill inspection using both classical machine learning and deep learning approaches.

The objective is to compare how different **data representations** influence anomaly detection performance, particularly across different defect types such as **structural damage (chips)** and **surface contamination (dirt)**.

---

## ⚙️ Methods

Two fundamentally different approaches were implemented and compared:

### 🔹 HOG + One-Class SVM
- Histogram of Oriented Gradients (HOG) for feature extraction  
- One-Class SVM (OCSVM) for anomaly detection  
- Focuses on capturing **edge and gradient structure**

---

### 🔹 Convolutional Autoencoder
- Learns representations directly from image data  
- Uses **reconstruction error** as an anomaly score  
- Designed to capture more complex patterns  

---

## 📊 Key Findings

- **Feature-based methods (HOG + OCSVM) performed better for structural defects** such as chipped pills  
- **Autoencoders struggled with subtle anomalies**, often reconstructing them too well  
- Detection performance was driven more by **representation quality** than model complexity  
- **Threshold selection** significantly impacted results, especially the trade-off between false positives and false negatives  

---

## 📈 Results Summary

| Metric   | HOG + OCSVM | Autoencoder |
|----------|-------------|-------------|
| ROC-AUC  | 0.981       | 0.966       |
| PR-AUC   | 0.998       | 0.995       |
| F1 Score | 0.938       | 0.816       |

- Both methods achieved strong ranking performance, but HOG + OCSVM delivered better overall anomaly detection performance in the final tuned comparison.

---

## 🖼 Example Outputs

### Reconstruction Heatmaps (Autoencoder)
- Highlights where the model struggles to reconstruct input  
- Structural defects produce higher reconstruction error  
- Subtle contamination is often smoothed out  

---

## 🧠 Key Insights

- Representation matters more than model complexity in anomaly detection  
- Reconstruction-based methods can fail when models generalise too well  
- Different anomaly types require different detection strategies  
- Evaluation should go beyond metrics and include **failure case analysis**

---

## 🛠 Tech Stack

- Python  
- PyTorch  
- scikit-learn  
- NumPy  
- Matplotlib  

---

## 🚀 Future Improvements

- Hybrid models combining feature-based and learned representations  
- Improved sensitivity to subtle anomalies  
- Evaluation on larger and more diverse datasets  
- More robust thresholding strategies  

---

## 📁 Project Structure
pill-anomaly-detection/
│
├── notebook/
│ └── anomaly_detection.ipynb
├── results/
│ ├── figures/
│ └── metrics.csv
├── assets/
│ └── sample_outputs.png
├── requirements.txt
└── README.md

---

## 📌 Notes

This repository presents a refined version of the project focused on practical insights, model behaviour, and real-world applicability.

---

⭐ If you found this interesting, feel free to explore the notebook and results for more detail.
