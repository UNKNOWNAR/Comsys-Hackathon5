Got it! Here’s a **complete single `README.md` file** you can copy-paste at once (just copy everything between the lines):

---

```markdown
# 🚀 Gender Classification under Adverse Visual Conditions
**COMSYS Hackathon-5, 2025 – Task A**

This repository contains our submission for **Task A: Gender Classification**.  
The goal is to build a robust deep learning model that can predict gender (Female/Male) from face images captured under challenging conditions (blur, fog, low light, rain, etc.) using the **FACECOM** dataset.

---

## 📂 Folder Structure

```

comsys-hackathon5/
├── README.md
├── requirements.txt
├── notebooks/
│ └── submission_notebook.ipynb
├── models/
│ ├── gender_classifier.weights.h5 # Model weights (NOT committed; see below)
│ └── female_threshold.txt # Saved threshold after tuning
└── .gitignore

````

---

## ⚙️ Setup & Dependencies

Install dependencies:
```bash
pip install -r requirements.txt
````

Dependencies include:

* TensorFlow >= 2.8
* scikit-learn
* numpy
* matplotlib
* seaborn

---

## 📦 Dataset

Download and place the FACECOM dataset in this structure:

```
/kaggle/input/facecom/Comys_Hackathon5/Task_A/
    ├── train/
    │   ├── female/
    │   └── male/
    └── val/
        ├── female/
        └── male/
```

---

## 🧪 How to Run

1. Open `notebooks/submission_notebook.ipynb` in Jupyter or Kaggle.
2. Run all cells – it will:

   * Preprocess data & augment images
   * Train the model using focal loss
   * Evaluate performance (accuracy, recall, F1-score, confusion matrix)
   * Fine-tune on hard samples
   * Find the best threshold for the female class
3. Save the trained model weights in `models/gender_classifier.weights.h5`.
4. Save the optimal threshold in `models/female_threshold.txt`.

---

## ✅ Using the Trained Model

To reload and test:

```python
# Rebuild model architecture
model = build_model()
# Load trained weights
model.load_weights('models/gender_classifier.weights.h5')
# Load saved threshold
with open('models/female_threshold.txt', 'r') as f:
    female_thresh = float(f.read().strip())
```

Use `predict_on_directory_with_threshold(test_dir, female_thresh)`
to get predictions on new test images.

---

## 📌 Key Features

* EfficientNetB0 backbone for feature extraction
* Focal Loss to handle class imbalance
* Aggressive data augmentation for robustness
* Fine-tuning on hard samples
* Threshold tuning to improve F1-score

---

## 📊 Results

All evaluation metrics (accuracy, precision, recall, F1-score, confusion matrix) are printed in the notebook.
Final predictions use the threshold-adjusted model.

---

## 📦 Model Weights

⚠️ Due to size limits, model weights are NOT included in the repository.
Please download from our shared cloud link (e.g., Google Drive) and place them in:

```
models/gender_classifier.weights.h5
models/female_threshold.txt
```

---

## 📞 Contact

For questions: **amiarinjaysarkar@gmail.com , srinjoymukherjee2005@gmail.com, gouravroy2110@gmail.com**

---

## 📝 License

This repository is part of COMSYS Hackathon-5, 2025 submission.
