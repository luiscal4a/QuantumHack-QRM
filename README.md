# Quantum Risk Management (QRM)
## Quantum Credit – Banco Santander Challenge

## Overview
This repository contains the implementation and experimental results of **Quantum Risk Management (QRM)**, developed for the *Quantum Credit* challenge proposed by **Banco Santander**.  
The project explores whether **quantum and hybrid quantum–classical machine learning models** can provide meaningful insights when compared to strong classical baselines for **credit risk prediction**, with a specific focus on **low-confidence and ambiguous decision regions**.

Rather than aiming for a global replacement of classical machine learning, the approach is **confidence-driven**, targeting precisely those cases where classical models exhibit uncertainty.

---

## Problem Statement
Credit default prediction is formulated as a **binary classification problem** using anonymized personal, financial, and loan-related features.

- Dataset size: **3,000 samples**
- Features include:
  - Borrower personal information
  - Loan characteristics
  - Financial ratios
- Target variable:
  - `0`: Non-default
  - `1`: Default

The reduced dataset size makes this scenario particularly suitable for evaluating quantum approaches in **small-data regimes**, aligned with the objectives of the Banco Santander challenge.

---

## Methodology

The project follows a structured four-step workflow:

### 1. Classical Baseline Modeling
Several classical models are trained under identical conditions to establish a reliable reference:

- XGBoost.
- Random Forest.
- Multilager percerption.

All models share the same preprocessing pipeline and a strict train–test split.  
Evaluation is performed exclusively on the test set using metrics such as Accuracy, AUC-ROC, F1-score, and Gini coefficient.

---

### 2. Confidence Analysis
Beyond global performance, **prediction confidence** is analyzed using probability outputs from the classical models.

Empirical results show that:
- Correct predictions exhibit **higher average confidence**
- Incorrect predictions show **lower average confidence**

This confirms that classical models struggle most near the **decision boundary**, motivating a targeted quantum approach.

---

### 3. Quantum Feature Embedding
Quantum embeddings are applied to expand the dimensionality of the data by mapping classical features into **high-dimensional Hilbert spaces** using parameterized quantum circuits.

The objective is to:
- Enhance feature representation
- Improve separability in low-confidence regions
- Maintain a hybrid quantum–classical workflow

Quantum circuits are trained using classical optimizers and **validated on real quantum hardware**.

---

### 4. Comparative Evaluation
Classical and quantum models are evaluated under identical experimental conditions.

Key observations:
- Global performance metrics remain comparable
- Quantum-enhanced models show **more stable behavior** across low-confidence samples
- Improvements are observed in robustness rather than overall accuracy

This indicates that quantum embeddings add value primarily in **ambiguous regions**, not as a universal replacement for classical models.

---


## Results Summary
- Classical models provide strong and reliable baselines
- Confidence analysis reveals limitations not visible in global metrics
- Quantum embeddings improve robustness in low-confidence regions
- The value of quantum models emerges under uncertainty

---

## Future Work
Further work will focus on refining quantum circuit design and feature encoding, with deeper analysis of low-confidence and borderline credit risk cases. Additional experiments will assess scalability beyond the small-data regime and strengthen confidence-driven hybrid quantum–classical pipelines.

---

## Repository Structure

- [Reduced-credit-risk-prediction.ipynb](Reduced-credit-risk-prediction.ipynb): Includes the example file created by Banco Santander.
- [Risk_pred_custom.ipynb](Risk_pred_custom.ipynb): Custom notebook created for classical ML tests and confidence analysis.
- [Get_Least_Confident.ipynb](Get_Least_Confident.ipynb): Notebook created to obtain the data with the least confidence from an XGBoost classification. 
- [SVM.ipynb](SVM.ipynb): Notebook to test inference on different SVM kernels.
- **csv files**: Different transformations of the data such as one-hot and ordinal encoding as well as scaling.
- [quantum_fan_out.ipynb](fan_out/quantum_fan_out.ipynb): Notebook for the data augmentation via quantum embedding.
- [zz_kernel_scripts](zz_kernel_scripts): Different auxiliary notebooks for comparison between default and quantum-augmented data.


---

## Team
**QRACKS – Quantum Risk Management**

- Luis de la Cal García  
- Luis Miguel Díaz López  
- Sabina Moreno Morlón  
- Paolo Allione  
- Edoardo Frulla  

---

## Final Note
> *Probably classical. Definitely curious.*
