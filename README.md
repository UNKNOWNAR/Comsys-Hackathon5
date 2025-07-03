# COMSYS Hackathon-5, 2025 – Overview  
**Face Intelligence Challenge – Task A & B Submission**

This repository contains our solutions to the **COMSYS Hackathon-5** organized around real-world facial intelligence problems. The competition features two primary tasks centered on deep learning for face-based classification and verification under challenging visual conditions.

---

## 🧠 Hackathon Challenge Overview

### 🔹 Task A: Gender Classification  
- **Objective**: Predict the gender (Male/Female) from face images under visual degradation such as blur, rain, fog, or low light.  
- **Type**: Binary Classification  
- **Input**: Images in `train/female`, `train/male` and similarly for validation  
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1 Score  

### 🔹 Task B: Face Verification  
- **Objective**: Verify whether two face images — one clean and one distorted — belong to the same identity.  
- **Type**: One-vs-One Matching (Binary Verification) and One-vs-Many (Gallery Classification)  
- **Input**: Each identity is a folder with clean images and a `distortion/` subfolder  
- **Evaluation Metrics**: Accuracy, Precision, Recall, F1 Score, ROC AUC, Gallery Top-1 Accuracy, Macro F1  

---

## ✅ Submission Checklist  
As per the hackathon guidelines, we have included:

- 📊 Evaluation metrics on the validation dataset for both tasks  
- 📁 Well-structured code notebooks for training and testing  
- 📦 Pretrained model weights (shared separately via Drive link)  
- 📝 README files for each track (Track_A and Track_B)  
- ✅ Test scripts accepting custom test folder inputs

---

## 🛠️ Our Solution Highlights

### 🟢 Track A – Gender Classification  
- **Model**: EfficientNetB0  
- **Loss Function**: Focal Loss to address class imbalance  
- **Techniques**:
  - Strong data augmentation
  - Threshold tuning on F1-score
  - Fine-tuning on hard examples  
- **Result**: High F1 score on validation with robust generalization under adverse conditions

### 🔵 Track B – Face Verification  
- **Model**: Siamese Network with ResNet-18 Backbone  
- **Modes**:
  - Standard RGB-based embedding similarity
  - Optional DCT/FFT attention-based evaluation (for spectral enhancement)  
- **Insights**:
  - DCT attention provided tighter t-SNE clusters but underperformed in actual matching
  - Cosine similarity used for gallery classification and binary verification  
- **Result**: Reliable performance across multiple distortion types; evaluation results saved and visualized


## 📞 Contact & Team Info

👨‍💻 **Team Members**:
- Arinjay Sarkar  
- Srinjoy Mukherjee  
- Gourav Roy  

🏫 **Institution**: *[Jadavpur University]*  
📧 **Emails**:
- amiarinjaysarkar@gmail.com  
- srinjoymukherjee2005@gmail.com  
- gouravroy2110@gmail.com  

---

## 📝 License
This repository is submitted as part of **COMSYS Hackathon-5, 2025** for Task A (Gender Classification) and Task B (Face Verification).  
All work is original and complies with the competition guidelines.