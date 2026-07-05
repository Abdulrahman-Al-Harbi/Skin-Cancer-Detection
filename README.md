# Skin Cancer Detection Using Fusion Deep Learning

A deep learning framework for automated skin cancer classification using **clinical skin images** and **patient clinical information**.

The proposed model combines **EfficientNetB3**, **Gray-World Color Constancy**, and **Squeeze-and-Excitation (SE) attention** to improve classification performance on the **PAD-UFES-20** dataset. The model is evaluated using **patient-level stratified 5-fold cross-validation** with ensemble prediction to prevent data leakage and provide reliable performance estimates.

---

## Features

- EfficientNetB3 transfer learning
- Gray-World color constancy preprocessing
- Fusion of image features and clinical metadata
- Squeeze-and-Excitation (SE) attention
- Patient-level stratified 5-fold cross-validation
- Ensemble prediction
- Class imbalance handling using weighted loss
- Performance evaluation using ROC curves and confusion matrix

---

## Dataset

This project uses the **PAD-UFES-20** skin cancer dataset.

### Dataset Summary

- **2,298** smartphone-acquired clinical images
- **1,373** patients
- **1,641** unique lesions
- **6** diagnostic categories

| Class | Images |
|--------|-------:|
| Basal Cell Carcinoma (BCC) | 845 |
| Actinic Keratosis (ACK) | 730 |
| Nevus (NEV) | 244 |
| Seborrheic Keratosis (SEK) | 235 |
| Squamous Cell Carcinoma (SCC) | 192 |
| Melanoma (MEL) | 52 |

The complete dataset can be downloaded from Kaggle:

https://www.kaggle.com/datasets/mahdavi1202/skin-cancer

> **Note:** The clinical images are not included in this repository because of their large size. Only the required metadata file is provided.

---

## Model Architecture

The proposed framework consists of two branches:

### Image Branch
- Gray-World color constancy
- EfficientNetB3 backbone
- SE attention
- Image feature extraction

### Clinical Branch
- Patient clinical metadata
- Fully connected neural network
- Clinical feature embedding

### Fusion
- Feature concatenation
- SE attention
- Fully connected classifier
- Softmax output for six skin lesion classes

---

## Training Strategy

- Transfer learning with EfficientNetB3
- Fine-tuning of the upper layers
- Patient-level Stratified Group 5-Fold Cross Validation
- Label smoothing
- Class-weighted loss
- Early stopping
- Learning rate reduction
- Ensemble averaging of five fold models

---

## Results

### Overall Performance

| Metric | Score |
|--------|-------|
| Accuracy | **73.86%** |
| Weighted Precision | **72.47%** |
| Weighted Recall | **73.86%** |
| Weighted F1-score | **72.74%** |
| Macro F1-score | **62.43%** |

### Per-class Performance

| Class | Precision | Recall | F1-score |
|------|---------:|-------:|---------:|
| ACK | 0.82 | 0.80 | 0.81 |
| BCC | 0.72 | 0.86 | 0.78 |
| MEL | 0.50 | 0.43 | 0.46 |
| NEV | 0.84 | 0.77 | 0.81 |
| SCC | 0.31 | 0.18 | 0.23 |
| SEK | 0.70 | 0.62 | 0.66 |

---

## Repository Structure

```text
skin_cancer_detection/
│
├── README.md
│
├── research_paper/
│   └── skin_cancer_research_paper.pdf
│
├── poster/
│   └── skin_cancer_poster.pdf
│
├── notebooks/
│   └── skin_cancer_detection_model.ipynb
│
├── data/
│   └── metadata.csv
│
└── results/
    ├── confusion_matrix.png
    ├── roc_curve.png
    ├── classification_report.txt
    └── final_metrics.csv
```

---

## Running the Project

1. Download the PAD-UFES-20 dataset.
2. Place the dataset inside the `data/` directory.
3. Open:

```
notebooks/skin_cancer_detection_model.ipynb
```

4. Update the dataset paths if necessary.
5. Run the notebook cells sequentially.

---

## Research Paper

The complete research paper is available in:

```
research_paper/
```

---

## Poster

The project poster is available in:

```
poster/
```

---

## Results

The generated evaluation files are available in:

```
results/
```

Including:

- Confusion Matrix
- ROC Curve
- Classification Report
- Final Evaluation Metrics

---

## Author

**Abdulrahman Alharbi**
