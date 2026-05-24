# Prediction of Formation Energy and Band Gap of Inorganic Photovoltaic Materials

Machine Learning based prediction of **Formation Energy (Ef)** and **Band Gap (Eg)** for inorganic perovskite photovoltaic materials using multiple regression and deep learning approaches. This project compares the performance of **Linear Regression**, **Support Vector Regression (SVR)**, and **Artificial Neural Networks (ANN)** on material science datasets derived from the Open Quantum Materials Database (OQMD). 

---

## 📌 Project Overview

The prediction of material properties such as **band gap** and **formation energy** is extremely important in discovering efficient and stable photovoltaic materials. Traditional approaches like **Density Functional Theory (DFT)** are computationally expensive and time intensive.

This project aims to accelerate material screening by using Machine Learning models to predict these properties directly from engineered material descriptors. 

---

## 🧪 About Perovskites

Perovskites are inorganic compounds with a general chemical formula:

ABX_3

where:

* **A and B** are cations
* **X** is an anion

These materials are widely used in photovoltaic applications because of:

* Tunable band gaps
* High charge carrier mobility
* Lightweight and flexible structures
* High solar conversion efficiency 

---

## 🎯 Objectives

* Predict **Formation Energy (Ef)**
* Predict **Band Gap (Eg)**
* Compare ML model performances
* Reduce dependency on expensive DFT calculations
* Build a scalable ML pipeline for materials discovery

---

## 📂 Dataset

* Source: **Open Quantum Materials Database (OQMD)**
* Total Samples: **16,323**
* Features Used: **57**
* Target Variables:

  * Formation Energy (Ef)
  * Band Gap (Eg) 

---

## ⚙️ ML Pipeline

The project follows the pipeline below:

1. Data Preprocessing
2. Feature Engineering
3. Feature Selection using RFE
4. Model Training
5. Hyperparameter Optimization
6. Error Evaluation

Additionally:

* Predicted **Formation Energy** is used as an additional feature for predicting **Band Gap**, improving model performance. 

---

## 🧹 Data Preprocessing

### Feature Elimination

Removed:

* `entry_id`
* `icsd_id`
* `rsp`
* `av_rsp`

because they either:

* lacked physical meaning, or
* required DFT calculations. 

### Feature Scaling & Encoding

* Standardization applied to numerical features
* Compound names encoded
* Space groups encoded based on lattice symmetry
* Crystal structures encoded using symmetry order 

### Feature Engineering

Created a new feature categorizing structures into:

* Centrosymmetric
* Non-centrosymmetric
* Enantiomorphic 

---

# 🤖 Models Used

## 1️⃣ Linear Regression

A baseline model to understand linear relationships between descriptors and target properties.

### Results

| Metric   | Ef     | Eg     |
| -------- | ------ | ------ |
| MSE      | 0.2736 | 1.2032 |
| RMSE     | 0.5231 | 1.0969 |
| R² Score | 0.6889 | 0.2478 |

Linear regression struggled to capture complex nonlinear relationships, especially for band gap prediction. 

---

## 2️⃣ Support Vector Regression (SVR)

SVR improved prediction accuracy by modeling nonlinear relationships and reducing sensitivity to outliers. 

### Results

| Metric   | Ef     | Eg     |
| -------- | ------ | ------ |
| MSE      | 0.1797 | 0.5889 |
| RMSE     | 0.4239 | 0.7674 |
| R² Score | 0.7974 | 0.6318 |

SVR significantly outperformed Linear Regression for both targets. 

---

## 3️⃣ Artificial Neural Network (ANN)

The ANN model achieved the best performance due to its ability to capture highly nonlinear relationships in materials data. 

### Key Features

* Keras Sequential API
* Dropout Regularization
* Hyperparameter tuning using Keras Tuner
* Adam Optimizer

### Results

| Metric   | Ef     | Eg     |
| -------- | ------ | ------ |
| MSE      | 0.0462 | 0.2803 |
| RMSE     | 0.2133 | 0.5241 |
| R² Score | 0.9471 | 0.8307 |

ANN achieved the highest accuracy among all models. 

---

## 📊 Model Comparison

| Model             | Ef R²  | Eg R²  |
| ----------------- | ------ | ------ |
| Linear Regression | 0.6889 | 0.2478 |
| SVR               | 0.7974 | 0.6318 |
| ANN               | 0.9471 | 0.8307 |

The ANN model provided the best predictive capability for both formation energy and band gap.

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Scikit-learn
* TensorFlow / Keras
* Matplotlib
* Keras Tuner

---

## 📈 Future Scope

* Include hybrid perovskites
* Expand descriptor database
* Integrate fingerprinting techniques
* Deploy web-based prediction interface
* Predict power conversion efficiency directly 

---

## 🚀 How to Run

```bash
# Clone repository
git clone <repo-link>

# Install dependencies
pip install -r requirements.txt

# Run training script
python train.py
```

---

## 📚 References

* Open Quantum Materials Database (OQMD)
* Research papers on Perovskite Photovoltaics
* Scikit-learn Documentation
* TensorFlow/Keras Documentation

---

## 👥 Contributors

* Apratim Mahapatra
* Atharva Kulkarni
* Rhythem Sood
* Vedant Kulkarni
* Vishwajeet Pawar 

---

## 🏫 Course Information

**Course:** MM5565 – Machine Learning in Material Science
**Department:** Metallurgical and Materials Engineering
**Institute:** Indian Institute of Technology Madras
**Year:** 2024
