# MachineLearning-vision-classifier
# Hybrid KNN-KMeans Handwritten Digit Recognition

## Overview
[cite_start]This project implements a robust machine learning pipeline to automate the recognition of handwritten digits (0-9)[cite: 7]. [cite_start]Addressing the challenge of high variance in human handwriting, the system utilizes a hybrid unsupervised-supervised learning framework to accurately classify images[cite: 6, 8]. [cite_start]The final optimized model achieves a classification accuracy of **98.61%**[cite: 10].

---

## Dataset
* [cite_start]**Source:** Optical Recognition of Handwritten Digits Dataset (Mini-MNIST) accessed via Scikit-Learn[cite: 23].
* [cite_start]**Size:** 1,797 samples of handwritten digits collected from 43 different people[cite: 25].
* [cite_start]**Features:** Raw 8x8 bitmap images flattened into 64-dimensional feature vectors, with pixel intensities scaled[cite: 18, 28].
* [cite_start]**Classes:** 10 distinct classes representing the digits 0 through 9[cite: 26].

---

## Methodology & Pipeline

### 1. Data Preprocessing
* [cite_start]**Train/Test Split:** The dataset is partitioned into an 80% Training Set and a 20% Testing Set using stratified sampling to prevent class imbalance[cite: 78, 79].
* [cite_start]**Normalization:** Min-Max Normalization is applied to scale all 64 feature vectors to a uniform range of [0, 1], ensuring equal contribution to distance calculations[cite: 82, 83].

### 2. Unsupervised Pattern Discovery (K-Means)
* [cite_start]**Elbow Method:** Validated the geometric separability of the dataset, confirming an optimal partition of `k=10` distinct groups[cite: 109, 143].
* [cite_start]**Silhouette Analysis:** Evaluated cluster cohesion and separation to identify inherently overlapping digits (e.g., '1', '8', '9')[cite: 8, 147].

### 3. Supervised Classification (KNN)
* [cite_start]**Model Optimization:** A K-Nearest Neighbors (KNN) classifier is optimized using Validation Curves to find the optimal neighbor count (k) that maximizes test accuracy and prevents overfitting[cite: 203, 205, 207].

---

## Results & Performance
* [cite_start]**Accuracy:** The final model correctly predicted 355 out of 360 test samples, resulting in a **98.61%** accuracy score[cite: 476].
* [cite_start]**Error Analysis:** Failure Mode Analysis revealed that misclassifications predominantly occurred in highly distorted edge cases (e.g., unusually slanted digits or broken loops) where patterns deviated significantly from cluster centroids[cite: 463, 538].

---

## Tech Stack & Dependencies
[cite_start]The following Python libraries were utilized for data manipulation, modeling, and visualization [cite: 31-35, 151, 260]:
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

---

## Author
[cite_start]**Harini P.** School of Computer Science and Engineering, VIT Chennai[cite: 4].
