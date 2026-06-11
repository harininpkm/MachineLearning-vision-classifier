# MachineLearning-vision-classifier
# Hybrid KNN-KMeans Handwritten Digit Recognition

## Overview
This project implements a robust machine learning pipeline to automate the recognition of handwritten digits (0-9). Addressing the challenge of high variance in human handwriting, the system utilizes a hybrid unsupervised-supervised learning framework to accurately classify images. The final optimized model achieves a classification accuracy of **98.61%**.

---

## Dataset
* **Source:** Optical Recognition of Handwritten Digits Dataset (Mini-MNIST) accessed via Scikit-Learn.
* **Size:** 1,797 samples of handwritten digits collected from 43 different people.
* **Features:** Raw 8x8 bitmap images flattened into 64-dimensional feature vectors, with pixel intensities scaled.
* **Classes:** 10 distinct classes representing the digits 0 through 9.

---

## Methodology & Pipeline

### 1. Data Preprocessing
* **Train/Test Split:** The dataset is partitioned into an 80% Training Set and a 20% Testing Set using stratified sampling to prevent class imbalance.
* **Normalization:** Min-Max Normalization is applied to scale all 64 feature vectors to a uniform range of [0, 1], ensuring equal contribution to distance calculations.

### 2. Unsupervised Pattern Discovery (K-Means)
* **Elbow Method:** Validated the geometric separability of the dataset, confirming an optimal partition of `k=10` distinct groups.
* **Silhouette Analysis:** Evaluated cluster cohesion and separation to identify inherently overlapping digits (e.g., '1', '8', '9').

### 3. Supervised Classification (KNN)
* **Model Optimization:** A K-Nearest Neighbors (KNN) classifier is optimized using Validation Curves to find the optimal neighbor count (k) that maximizes test accuracy and prevents overfitting.

---

## Results & Performance
* **Accuracy:** The final model correctly predicted 355 out of 360 test samples, resulting in a **98.61%** accuracy score.
* **Error Analysis:** Failure Mode Analysis revealed that misclassifications predominantly occurred in highly distorted edge cases (e.g., unusually slanted digits or broken loops) where patterns deviated significantly from cluster centroids.

---

## Tech Stack & Dependencies
The following Python libraries were utilized for data manipulation, modeling, and visualization :
* `pandas`
* `numpy`
* `matplotlib`
* `seaborn`
* `scikit-learn`

---

## Author
**Harini P.** School of Computer Science and Engineering, VIT Chennai.
