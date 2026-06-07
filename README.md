# Klasifikasi Penyakit Common Rust, Northern Leaf Blight, dan Gray Leaf Spot pada Citra Daun Jagung Menggunakan Ekstraksi Fitur GLCM dan Transformasi Wavelet dengan Metode KNN, SVM, dan Random Forest

## Nama Anggota

| Nama                     | NIM        |
| -------------------------| ---------- |
| LALU TAUFIK DEWO BAYUAJI | F1D02410069|
| RIVAL HOSAM WILMADANI| F1D02410091 |
| ALYA RASYIDA PUTRI | F1D02410002|
| SAMARA WARDASADIYA| F1D02410023|

---

## Project Overview

Pada project Pengolahan Citra Digital (PCD) ini dilakukan klasifikasi penyakit daun jagung menggunakan teknik ekstraksi fitur **Gray Level Co-occurrence Matrix (GLCM)** dan **Transformasi Wavelet**, serta membandingkan performa tiga algoritma machine learning yaitu **K-Nearest Neighbor (KNN)**, **Support Vector Machine (SVM)**, dan **Random Forest**.

Penyakit yang diklasifikasikan terdiri dari:

* Common Rust
* Northern Leaf Blight
* Gray Leaf Spot

Tujuan utama dari project ini adalah:

* Mengimplementasikan teknik pengolahan citra digital untuk klasifikasi penyakit tanaman.
* Menganalisis pengaruh preprocessing terhadap performa model klasifikasi.
* Mengekstraksi fitur tekstur menggunakan GLCM dan fitur frekuensi menggunakan Transformasi Wavelet.
* Membandingkan performa model KNN, SVM, dan Random Forest pada dataset penyakit daun jagung.

Dataset yang digunakan berasal dari Kaggle:

**Corn or Maize Leaf Disease Dataset**

https://www.kaggle.com/datasets/smaranjitghose/corn-or-maize-leaf-disease-dataset

---

## Dataset Information

Dataset terdiri dari citra daun jagung yang terbagi ke dalam beberapa kelas penyakit:

| Kelas                | Deskripsi                                      |
| -------------------- | ---------------------------------------------- |
| Common Rust          | Penyakit akibat jamur *Puccinia sorghi*        |
| Northern Leaf Blight | Penyakit akibat jamur *Exserohilum turcicum*   |
| Gray Leaf Spot       | Penyakit akibat jamur *Cercospora zeae-maydis* |

Setiap citra akan melalui proses preprocessing, ekstraksi fitur, dan klasifikasi menggunakan model machine learning.

---

## Project Workflow

### 1. Import Library

Mengimpor library yang dibutuhkan untuk:

* Pengolahan citra
* Visualisasi data
* Ekstraksi fitur
* Machine Learning

Contoh library:

```python
import cv2
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.neighbors import KNeighborsClassifier
from sklearn.svm import SVC
from sklearn.ensemble import RandomForestClassifier

from skimage.feature import graycomatrix, graycoprops
import pywt
```

### 2. Load Dataset

Membaca seluruh citra dari dataset beserta labelnya.

```python
data = []
labels = []
file_name = []
```

Tahapan yang dilakukan:

* Membaca seluruh gambar dari folder dataset.
* Melakukan resize agar ukuran citra seragam.
* Menyimpan citra dan label ke dalam array.

---

### 3. Data Understanding

Eksplorasi data dilakukan untuk memahami karakteristik dataset.

Analisis yang dilakukan:

* Jumlah data setiap kelas.
* Distribusi data.
* Visualisasi sampel citra.
* Kondisi pencahayaan.
* Noise pada citra.
* Karakteristik tekstur penyakit.

Contoh visualisasi:

* Distribusi jumlah data per kelas.
* Contoh citra dari masing-masing kelas.
* Histogram citra.

---

### 4. Preprocessing

Tahapan preprocessing dilakukan secara bertahap pada setiap percobaan.

Contoh preprocessing yang digunakan:

1. Resize
2. Grayscale Conversion / Pemisahan Chanel RGB
3. Median Filtering
4. Thresholding / Segmentasi

---

## Experiment Scenario

### Percobaan 1

Preprocessing:

* Resize
* Grayscale
* Median

Feature Extraction:

* GLCM
* Wavelet

Model:

* KNN
* SVM
* Random Forest

---

### Percobaan 2

Preprocessing:

* Resize
* Grayscale
* Median Filtering
* Edge Detection Sobel + Robert

Feature Extraction:

* GLCM
* Wavelet

Model:

* KNN
* SVM
* Random Forest

---

### Percobaan 3

Preprocessing:

* Resize
* Grayscale
* Median Filtering
* Edge Detection Sobel + Robert
* Thresholding / Segmentasi
* Closing + Opening

Feature Extraction:

* GLCM
* Wavelet

Model:

* KNN
* SVM
* Random Forest

### Percobaan 4

Preprocessing:

* Resize
* Pemisahan Chanel R
* Sharpening
* Smoothing

Feature Extraction:

* GLCM
* Wavelet

Model:

* KNN
* SVM
* Random Forest

### Percobaan 5

Preprocessing:

* Resize
* Pemisahan Chanel G
* Pemisahan Chanel B
* Sharpening
* Smooting

Feature Extraction:

* GLCM
* Wavelet

Model:

* KNN
* SVM
* Random Forest

---

## Feature Extraction

### Gray Level Co-occurrence Matrix (GLCM)

Fitur tekstur yang digunakan:

* Contrast
* Correlation
* Energy
* Homogeneity

### Wavelet Transform

Menggunakan Discrete Wavelet Transform (DWT) untuk memperoleh:

* Approximation Coefficients (LL)
* Horizontal Detail (LH)
* Vertical Detail (HL)
* Diagonal Detail (HH)

---

## Classification Models

### K-Nearest Neighbor (KNN)

Metode klasifikasi berbasis jarak antar data.

### Support Vector Machine (SVM)

Metode klasifikasi yang mencari hyperplane optimal untuk memisahkan kelas.

### Random Forest

Metode ensemble yang menggabungkan banyak decision tree untuk meningkatkan performa klasifikasi.

---

## Evaluation Metrics

Evaluasi model dilakukan menggunakan:

* Accuracy
* Precision
* Recall
* F1-Score
* Confusion Matrix

---

## Conclusion

[   ]

---

## Repository Structure

```text
├── notebooks/
│   ├── experiment_1.ipynb
│   ├── experiment_2.ipynb
│   └── experiment_3.ipynb
│
├── dataset/
│
├── images/
│
├── README.md
│
└── requirements.txt
```
