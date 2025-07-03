# Face Verification using Siamese Networks  
**COMSYS Hackathon-5, 2025 – Task B**  

This repository contains our submission for Task B: Face Verification.  
The objective is to verify whether a distorted face image and a clean image belong to the same identity using a Siamese network trained on the FACECOM dataset.

## 📂 Folder Structure
```
comsys-hackathon5/Track_B/
├── README.md
├── requirements.txt
├── notebooks/
├── facecom_modeltesting_withdct.ipynb # Evaluation with DCT-based attention
└── facecom-modeltesting.ipynb # Standard evaluation (recommended)
```


## 📦 Dataset Setup

Place the FACECOM dataset in this structure:
```
Comys_Hackathon5/Task_B/
├── train/
│ ├── Identity_001/
│ └── Identity_002/
│ └── distortion/
├── val/
│ ├── Identity_003/
│ └── Identity_004/
└── distortion/
```

or the Test directory as per your requirements

Each identity contains clean images and a `distortion/` subfolder with distorted versions.

## 🧠 Model Architecture

We use a Siamese Network architecture with **ResNet‑18** as the feature extractor backbone. Two parallel image branches share weights and output embeddings, compared using either:
- Cosine similarity (gallery) 
- Verification head (binary classification)

We trained two versions:
1. **Baseline** – Standard Siamese model using RGB image pairs
2. **DCT-Attention** – Siamese model evaluated with FFT/DCT-based frequency-domain attention maps

## 🧪 How to Run

1. Open evaluation notebooks:  
   - `facecom_modeltesting.ipynb` 
   - `facecom_modeltesting_withdct.ipynb` 

## 📌 Current Status of Notebooks

The provided notebooks are preloaded with our final evaluation results on the validation set.  
🔒 **Note**: The validation set was **strictly used for evaluation only** — no training or fine-tuning was performed on it.


## ✅ Evaluation Modes

**1. Gallery/Probe Classification**  
- Clean images as gallery  
- Distorted queries compared using cosine similarity  
- *Metrics:* Top‑1 Accuracy, Macro F1-score  

**2. Binary Verification**  
- Pairs classified as "same identity" or "different"  
- *Metrics:* Accuracy, Precision, Recall, F1-score, ROC AUC  

## ⚠️ About DCT Attention Evaluation

We explored FFT/DCT attention maps for enhancing embeddings in the frequency domain. These techniques can emphasize high-frequency spatial details — potentially improving the model’s focus on fine-grained facial features and texture patterns, which are often critical in distinguishing identities.

However, despite their theoretical appeal, our experiments highlighted several practical limitations:

**Limitations of DCT-based Evaluation:**
- High storage overhead due to the need to cache attention maps for each image
- Increased computational cost during inference
- Reduced robustness under distortions such as blur, compression, or lighting changes
- Inconsistency between training and inference representations (attention not used during training)

📌 *Despite promising t‑SNE visualizations showing tighter embedding clusters, DCT attention yielded slightly lower verification performance and less reliable cosine similarity scores in distorted scenarios.*


## 📊 Validation Results

### ✅ Standard Siamese (Recommended)
| Metric           | Value   |
|------------------|---------|
| Top‑1 Accuracy   | 0.7251  |
| Precision        | 0.8035  |
| Recall           | 0.5960  |
| F1 Score         | 0.6844  |
| ROC AUC          | 0.8423  |
| Gallery Accuracy | 0.5272  |
| Gallery Macro F1 | 0.6396  |

### ⚙️ With DCT Attention
| Metric           | Value   |
|------------------|---------|
| Top‑1 Accuracy   | 0.7167  |
| Precision        | 0.7939  |
| Recall           | 0.5855  |
| F1 Score         | 0.6739  |
| ROC AUC          | 0.8396  |
| Gallery Accuracy | 0.4754  |
| Gallery Macro F1 | 0.5742  |

## 🔒 Validation Usage Policy
- The validation set was used only for final evaluation by us to provide us a sanity check
- No training/fine-tuning was performed on validation data  
- All evaluation results are saved and reproducible through provided notebooks  

## 📌 Key Features
- ResNet‑18 backbone  
- Siamese pairwise training with mixed-precision  
- Evaluation on both binary verification and gallery-classification tasks  
- Optional FFT/DCT attention mechanism  
- Cosine similarity scoring and threshold optimization  
- Comprehensive plots provided to allow for better inferencing  

## 📦 Model Weights
⚠️ *Due to size restrictions, model weights are not included in the repository. Please download them from our shared drive link (provided during submission) and place them appropriately.*

## 📞 Contact
For queries, contact:  
amiarinjaysarkar@gmail.com,  
srinjoymukherjee2005@gmail.com,  
gouravroy2110@gmail.com  

## 📝 License
This repository is part of COMSYS Hackathon-5, 2025 submission for Track B.
