# Statistical Pattern Recognition in Single-Cell RNA-seq (PBMC3K)

## 🎯 Project Overview

This repository contains the full analysis pipeline for a university project focused on applying and evaluating classic statistical pattern recognition methods to high-dimensional single-cell RNA sequencing (scRNA-seq) data.

The primary goal was to automatically classify peripheral blood mononuclear cells (PBMCs) from the **pbmc3k dataset** and rigorously benchmark various linear and non-linear machine learning classifiers based on the theoretical concepts defined in the course syllabus.

## 🚀 Methodology & Academic Context

The project follows a comprehensive pipeline, where each computational step is mapped to a specific theoretical concept from the Statistical Pattern Recognition course syllabus.

| Pipeline Phase | Key Code Step | Syllabus Concept |
| :--- | :--- | :--- |
| **Data Definition** | `sc.datasets.pbmc3k()` | **Bod 1:** Třída, Vzor, Příznakový popis |
| **Preprocessing** | `sc.pp.filter_cells`, `sc.pp.scrublet` | **Bod 7:** Lineární transformace (Normalizace) |
| **Feature Engineering** | `sc.pp.highly_variable_genes` | **Bod 3:** Kvalita příznakového popisu (HVGs) |
| **Dimensionality Reduction** | `sc.tl.pca` | **Bod 7:** PCA |
| **Unsupervised Learning** | `sc.tl.leiden`, `sc.tl.kmeans` | **Bod 9:** Využití metrik (k-NN, c-mean) |
| **Model Optimization** | `GridSearchCV(cv=5)` | **Bod 6:** Metodika křížové validace |
| **Linear Classification** | `LDA`, `LogisticRegression` | **Bod 4:** LDA, **Bod 11:** Logistická regrese |
| **Non-Linear Classification** | `SVC`, `KNeighborsClassifier` | **Bod 9, 13:** Jádrové funkce (Kernels), k-NN |

## 📊 Key Results & Conclusion

The benchmark demonstrated that all models achieved an accuracy of over 97%, confirming the robustness of the data engineering pipeline. The highest performance was achieved by the simplest methods.

| Model | Classification Approach | Test Accuracy | F1-Score (Macro) |
| :--- | :--- | :--- | :--- |
| **LDA (Winner)** | **Linear / Generative** | **98.85 %** | **0.99** |
| **k-NN** | Non-parametric / Metric | 98.66 % | 0.99 |
| **SVM** | Non-linear / Kernel | 97.89 % | 0.97 |

The project concludes that the optimal classifier for this specific feature space is the **Linear Discriminant Analysis (LDA)**. This confirms that robust feature engineering successfully linearized the complex biological structure, allowing a powerful linear model to find near-perfect separation boundaries.

---

## 📂 Repository Structure

The project is driven by a single Jupyter Notebook file. All generated outputs are stored in a consistent folder structure, ensuring reproducibility.
