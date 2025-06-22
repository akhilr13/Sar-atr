# 🌌 SAR-ATR: Synthetic Aperture Radar Automatic Target Recognition

> A deep learning-based framework for **Automatic Target Recognition (ATR)** using **Synthetic Aperture Radar (SAR)** imagery. Combines **self-supervised learning** and **multi-scale feature extraction**, achieving **99.77% accuracy** on the MSTAR dataset — surpassing state-of-the-art methods.

---
## 📄 Paper & Citation

📘 This work was published in the **2024 IEEE India Geoscience and Remote Sensing Symposium (InGARSS)**.

If you use this work in your research, please cite:

```bibtex
@INPROCEEDINGS{10984364,
  author={Ashad Vali, P and Akhil, R and Chetana, K S and Vijayashekhar, S S},
  booktitle={2024 IEEE India Geoscience and Remote Sensing Symposium (InGARSS)}, 
  title={SAR Reconnaissance: Unveiling Target Recognition Via Pretext and Downstream Methodologies}, 
  year={2024},
  pages={1-4},
  keywords={Image recognition;Target recognition;Refining;Estimation;Reconnaissance;Network architecture;Radar polarimetry;Robustness;Real-time systems;Synthetic aperture radar;Synthetic Aperture Radar;Automatic target recognition;Moving and Stationary Target Acquisition and Recognition},
  doi={10.1109/InGARSS61818.2024.10984364}
}

## 🚀 Key Features

- 📡 Tailored for SAR imagery, robust under low visibility and noise
- 🧠 Pretext model with **Frost filter** + **multi-scale orientation learning**
- 🔍 Downstream classifier for final ATR with minimal labeled data
- 📊 Tested on MSTAR dataset — 11-class SAR data
- 🎯 Outperforms major SOTA models with 99.77% accuracy

---

## 🧠 Methodology Overview

### 🔧 Pretext Task (Unsupervised)
- Uses Frost filter to reduce speckle noise and highlight spatial structure
- Learns orientation & multi-scale features
- Includes 3 convolution + pooling blocks and 1 dense layer

### 📘 Downstream Task (Supervised)
- Learns from features extracted during pretext phase
- Contains 2 convolution + pooling blocks and 8 dense layers

> Total Layers: 20 (8 pretext + 12 downstream)  
> Activation: ReLU | Optimizer: Adam

---

## 📊 Experimental Results

| Method                          | Accuracy (%) |
|--------------------------------|--------------|
| Baseline CNN                   | 92.30        |
| Data Augmentation              | 93.16        |
| Gabor Filter                   | 96.32        |
| Bayesian Deep Learning         | 98.02        |
| Multi-view Network             | 98.52        |
| Self-Supervised Deep Network   | 98.90        |
| **Proposed Model (Ours)**      | **99.77**    |

- Dataset: MSTAR (158×158 px, 6200 SAR images, 11 classes)
- Data split: 70% Train, 20% Test, 10% Validation
- Evaluation: Accuracy, ROC, Confusion Matrix

---

## 💻 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/akhilr13/Sar-atr.git
   cd Sar-atr
2. **Install dependencies**
   ```bash
    pip install -r requirements.txt
   
4. **Run the notebook**
   ```bash
   jupyter notebook saratr.ipynb




