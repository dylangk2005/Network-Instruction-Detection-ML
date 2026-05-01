# 🛡️ Network Intrusion Detection System using Machine Learning

A real-time Network Intrusion Detection System (NIDS) built with Machine Learning on the CIC-IDS2017 dataset.

## 📌 Project Overview

This project detects network attacks in real-time by analyzing network flow features using multiple ML models. The best-performing model (Random Forest) is deployed to simulate real-time traffic analysis and alert generation.

## 📊 Dataset

- **Name:** CIC-IDS2017
- **Source:** [Kaggle](https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset)
- **Size:** 2,830,743 rows | 79 features
- **Classes:** BENIGN + 14 attack types (DDoS, DoS, PortScan, etc.)

## 🏗️ Project Architecture

```
├── Network_IDS_ML.ipynb    # Main notebook
├── alerts.log              # Real-time alert log
├── attack_distribution.png # EDA visualization
├── correlation_heatmap.png # Feature correlation heatmap
├── confusion_matrix_rf.png # Random Forest confusion matrix
└── README.md
```

## ⚙️ Installation

```bash
pip install -r requirements.txt
```

**requirements.txt:**
```
pandas
numpy
matplotlib
seaborn
scikit-learn
imbalanced-learn
joblib
```

## 🚀 Usage

1. Download dataset from Google Drive: [CIC-IDS2017 Dataset](https://drive.google.com/drive/folders/1h31ss_Q67yoDYEXJXklHgbzbxNMJV-2s?usp=sharing)
2. Upload the dataset to your Google Drive at the following path: `My Drive/IDS_Dataset/`
3. Open `Network_IDS_ML.ipynb` in Google Colab
4. Mount Google Drive and run all cells sequentially
5. Real-time alerts will be printed to console and saved in `alerts.log`

## 🤖 Model Comparison

| Model | Accuracy | Macro F1 | Training Time |
|---|---|---|---|
| Naive Bayes | 26% | 0.29 | ~1s |
| Logistic Regression | 79% | 0.32 | ~277s |
| SVM (LinearSVC) | 80% | 0.33 | ~980s |
| KNN | 97% | 0.67 | ~2129s |
| **Random Forest** ⭐ | **99%** | **0.78** | ~162s |

> ✅ **Random Forest** was selected as the best model due to having the highest accuracy (99%), the best F1-score (0.78), and a reasonable training time.

## 🚨 Real-time Alert Example

```
[ALERT] 2026-05-01T04:40:17 | Suspicious traffic detected: PortScan | SRC: 192.168.112.71 → DST: 10.0.50.9:80 | Severity: HIGH
[ALERT] 2026-05-01T04:40:17 | Suspicious traffic detected: DoS Hulk | SRC: 192.168.237.187 → DST: 10.0.65.71:22 | Severity: HIGH
```

## 💾 Saved Model

Random Forest model (~400MB) is available on Google Drive:
> 📁 [Download random_forest_ids.pkl](https://drive.google.com/drive/folders/1h31ss_Q67yoDYEXJXklHgbzbxNMJV-2s?usp=sharing)

## 📚 References

- https://github.com/marxgoo/Network-intrusion-detection-ml
- https://www.kaggle.com/datasets/chethuhn/network-intrusion-dataset
- https://www.kaggle.com/code/ujjwalks9/intrusion-detection-system
