# 👕 Myntra Size Recommendation ML

An **AI-based clothing size recommendation system** that predicts the most suitable clothing size for an online shopper using supervised machine learning.

The project is designed as an academic machine learning application inspired by online fashion retail. It uses a **Random Forest Classifier** to predict one of six clothing sizes: **XS, S, M, L, XL, or XXL**.

> **Note:** This project uses a synthetic dataset for academic purposes. No real Myntra or customer data was used.

---

## 🎯 Problem Statement

Online shoppers cannot physically try clothing before purchasing. Differences in sizing between brands and product categories can lead to:

* High product return rates
* Customer dissatisfaction
* Cart abandonment
* Increased reverse-logistics costs
* Unnecessary environmental impact

This project aims to provide a personalized size recommendation before purchase.

---

## 💡 Solution

The system treats clothing-size prediction as a **supervised classification problem**.

A Random Forest Classifier analyzes customer and purchase-related information and predicts the most suitable clothing size.

### Predicted Sizes

`XS` · `S` · `M` · `L` · `XL` · `XXL`

---

## 📊 Dataset

The project uses a **synthetic dataset** created to simulate realistic customer and product information.

| Dataset Detail   | Value |
| ---------------- | ----: |
| Total Records    | 2,500 |
| Training Records | 2,000 |
| Testing Records  |   500 |
| Input Features   |    10 |
| Target Classes   |     6 |
| Train/Test Split | 80/20 |

Synthetic data was selected to avoid using private customer information and to make the project suitable for academic experimentation.

---

## 🔢 Input Features

The model uses the following signals:

* Age
* Gender
* Height (cm)
* Weight (kg)
* Previous Size
* Brand
* Category
* Fit Preference
* Previous Purchases
* Previous Returns

The target variable is the recommended clothing size.

---

## 🧠 Machine Learning Workflow

```text
Raw Dataset
     ↓
Exploratory Data Analysis
     ↓
Data Cleaning
     ↓
Feature Preprocessing
     ↓
Train/Test Split
     ↓
Random Forest Classifier
     ↓
Model Evaluation
     ↓
Size Prediction
```

### Preprocessing

The workflow includes:

1. Exploring feature distributions
2. Handling missing or inconsistent values
3. Encoding categorical variables
4. Scaling numeric features where required
5. Performing an 80/20 stratified train-test split

---

## 🌳 Model

### Random Forest Classifier

The project uses a **Random Forest Classifier**, an ensemble machine learning algorithm based on multiple decision trees.

Model configuration:

```text
n_estimators = 100
class_weight = balanced
random_state = 42
```

Random Forest was selected because it can work effectively with a mixture of numerical and categorical features and provides useful feature-importance information.

---

## 📈 Model Performance

### Accuracy

| Metric            | Result |
| ----------------- | -----: |
| Training Accuracy |   100% |
| Testing Accuracy  |  62.4% |

The 100% training accuracy indicates a potential **overfitting issue**, making the test accuracy the more meaningful measure of performance.

The six-class random-chance baseline is approximately **16.7%**, while the model achieved **62.4% test accuracy**.

---

## 📋 Classification Performance

| Size | Precision | Recall | F1-Score |
| ---- | --------: | -----: | -------: |
| XS   |      0.00 |   0.00 |     0.00 |
| S    |      0.59 |   0.26 |     0.36 |
| M    |      0.65 |   0.77 |     0.70 |
| L    |      0.54 |   0.60 |     0.57 |
| XL   |      0.70 |   0.68 |     0.69 |
| XXL  |      0.67 |   0.20 |     0.31 |

The model performs better on the more common **M, L and XL** classes, while XS and XXL have fewer test examples.

---

## 🔍 Feature Importance

The three strongest signals identified by the model were:

| Feature       | Importance |
| ------------- | ---------: |
| Previous Size |      17.2% |
| Weight        |      14.6% |
| Height        |       9.9% |

### Key Insight

**Previous Size** was the strongest predictor, suggesting that a customer's historical size can provide valuable information when making a future recommendation.

---

## 💼 Business Value

A size recommendation system could potentially help fashion retailers:

* 📦 Reduce size-related returns
* ❤️ Improve customer satisfaction and loyalty
* 🛒 Increase purchase confidence
* 📊 Improve inventory and sizing decisions
* 🎯 Provide personalized shopping experiences

The intended experience is to show a personalized recommendation such as:

```text
Recommended Size: M

Based on your profile and previous purchases,
M is the predicted best-fit size.
```

---

## ⚠️ Limitations

This project has several important limitations.

### Synthetic Data

The dataset does not represent actual customer behavior and may not capture the complexity of real-world sizing across different brands, garments, and body types.

### Small Dataset

The dataset contains only 2,500 records compared with the millions of transactions that a large fashion platform may have.

### Overfitting

The model achieves 100% training accuracy but only 62.4% testing accuracy, indicating potential overfitting.

### Fixed Size Categories

The system predicts only:

`XS, S, M, L, XL, XXL`

It does not currently provide custom measurements or made-to-measure recommendations.

### No Live Feedback Loop

The current system does not continuously learn from whether a recommended size was actually a good fit.

---

## 🚀 Future Scope

Possible improvements include:

1. Collecting real and anonymized body-measurement data
2. Adding garment-specific measurements
3. Including fabric stretch and garment-cut information
4. Using customer return and exchange feedback
5. Building a continuous learning/feedback loop
6. Testing additional machine learning algorithms
7. Improving performance on rare size classes
8. Deploying the model through an interactive web application

---

## 🛠️ Suggested Technology Stack

* **Python**
* **Pandas**
* **NumPy**
* **Scikit-learn**
* **Matplotlib / Seaborn**
* **Jupyter Notebook**
* **Streamlit** for an interactive demo

---

## 📁 Suggested Project Structure

```text
myntra-size-recommendation-ml/
│
├── data/
│   └── synthetic_size_dataset.csv
│
├── notebooks/
│   └── size_recommendation.ipynb
│
├── src/
│   ├── preprocessing.py
│   ├── train_model.py
│   └── predict.py
│
├── app/
│   └── app.py
│
├── models/
│   └── random_forest_model.pkl
│
├── requirements.txt
├── README.md
└── LICENSE
```

---

## ▶️ How to Run

### 1. Clone the repository

```bash
git clone https://github.com/your-username/myntra-size-recommendation-ml.git
cd myntra-size-recommendation-ml
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Train the model

```bash
python src/train_model.py
```

### 4. Run the application

If the Streamlit demo is included:

```bash
streamlit run app/app.py
```

---

## 🎓 Academic Project

**Project:** AI-Based Smart Clothing Size Recommendation System
**Domain:** Machine Learning / Fashion Technology / FinTech & AI
**Model:** Random Forest Classifier
**Dataset:** Synthetic
**Program:** BBA Fintech & AI
**Institution:** Chitkara Business School

---

## 📌 Disclaimer

This is an academic machine learning project and is **not an official Myntra product or system**. The dataset is synthetic and does not contain real Myntra or customer data.

---

## ⭐ Key Takeaway

This project demonstrates how machine learning can transform basic customer and purchase information into a personalized clothing-size recommendation while highlighting the importance of **model evaluation, feature importance, data quality, and real-world limitations**.
