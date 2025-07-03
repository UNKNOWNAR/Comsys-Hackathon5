```markdown
 Gender Classification under Adverse Visual Conditions
**COMSYS Hackathon-5, 2025 – Task A**

This repository contains our submission for **Task A: Gender Classification**.  
The goal is to build a robust deep learning model that can predict gender (Female/Male) from face images captured under challenging conditions (blur, fog, low light, rain, etc.) using the **FACECOM** dataset.
````

## 📂 Folder Structure
````
comsys-hackathon5/Track_A
├── README.md
├── requirements.txt
├── notebooks/
│ └── track-a-test-script.ipynb
│ └── track_a_gender-classification.ipynb
├── models/
│ ├── gender_classifier.weights.h5 # Model weights (NOT committed; see below) so .txt files available
│ └── female_threshold.txt # Saved threshold after tuning
└── .gitignore
````

## 📦 Dataset

Download and place the FACECOM dataset in this structure:

````
Comys_Hackathon5/Task_A/
    ├── train/
    │   ├── female/
    │   └── male/
    └── val/
        ├── female/
        └── male/

````
🏋️‍♂️ Model Testing

````
Option 1: Download Pretrained Model and Threshold
If you want to skip training, you can use the provided pretrained model and threshold:

Download the model weights:
Download gender_classifier.weights.h5

Download the optimal threshold:
Download female_threshold.txt

Place both files in the models/ directory of your project:

text
C:\Users\amiar\Downloads\Comsys-Hackathon5\Track_A\models\
    gender_classifier.weights.h5
    female_threshold.txt
Option 2: Train the Model Yourself
Open the notebook:
C:\Users\amiar\Downloads\Comsys-Hackathon5\Track_A\notebooks\track_a_gender-classification.ipynb
(or, for testing, use track-a-test-script.ipynb)

Run all cells – the notebook will:

Preprocess and augment the data

Train the model using focal loss

Evaluate performance (accuracy, recall, F1-score, confusion matrix)

Fine-tune on hard samples

Find the best threshold for the female class

After training completes:

The trained model weights will be saved as
C:\Users\amiar\Downloads\Comsys-Hackathon5\Track_A\models\gender_classifier.weights.h5

The optimal threshold will be saved as
C:\Users\amiar\Downloads\Comsys-Hackathon5\Track_A\models\female_threshold.txt

Folder Structure Reminder:

text
Comsys-Hackathon5/
└── Track_A/
    ├── notebooks/
    │   ├── track_a_gender-classification.ipynb
    │   └── track-a-test-script.ipynb
    ├── models/
    │   ├── gender_classifier.weights.h5
    │   └── female_threshold.txt
    └── ...
Choose either option above. If you train your own model, make sure the weights and threshold files are saved in the models/ directory as shown.
````

Using the Trained Model

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
