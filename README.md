# ArabicSentimentLens 🇪🇬🤖

**Arabic Sentiment Analysis using TF-IDF and Linear SVM**

ArabicSentimentLens is an end-to-end Arabic Natural Language Processing (NLP) project for classifying Arabic reviews as **Positive** or **Negative**.

The project covers the complete machine learning workflow, from data cleaning and exploratory analysis to model training, evaluation, inference, browser-based deployment, and live testing.

---

## 🚀 Live Demo

🌐 **Try ArabicSentimentLens live:**

https://huggingface.co/spaces/abddoredaa222/ArabicSentimentLens

The model runs directly in the browser using JavaScript, with no backend inference server required.

---

## 📓 Kaggle Notebook

The complete project workflow is available on Kaggle:

https://www.kaggle.com/code/arbhdmoa22/arabicsentimentlens

The notebook contains the full pipeline, experiments, evaluation, model export, browser validation, and deployment preparation.

---

## 📌 Project Overview

The goal of this project is to build a lightweight and effective sentiment analysis system for Arabic reviews.

### Pipeline

```text
Arabic Reviews
      ↓
Data Cleaning
      ↓
Exploratory Data Analysis
      ↓
Arabic Text Preprocessing
      ↓
TF-IDF Feature Extraction
      ↓
Logistic Regression Baseline
      ↓
Linear SVM
      ↓
Model Evaluation
      ↓
Error Analysis
      ↓
Inference Testing
      ↓
Model Export
      ↓
Browser Inference
      ↓
Hugging Face Deployment
```

---

## 📊 Dataset

The project uses the **330K Arabic Sentiment Reviews Dataset** from Kaggle.

### Final Dataset

| Property              |   Value |
| --------------------- | ------: |
| Original reviews      | 330,000 |
| Final cleaned reviews | 329,967 |
| Negative reviews      | 163,123 |
| Positive reviews      | 166,844 |
| Training samples      | 263,973 |
| Test samples          |  65,994 |
| Classes               |       2 |

The dataset is almost perfectly balanced between positive and negative reviews.

---

## 🧹 Data Preprocessing

The preprocessing pipeline includes:

* HTML tag removal
* URL removal
* Alef normalization
* Arabic diacritics removal
* Tatweel removal
* Whitespace normalization
* Duplicate removal
* Very short review filtering

Arabic characters such as **ة** and **ى** were preserved because they carry linguistic information.

---

## 🔤 Feature Engineering

Text was transformed using **TF-IDF** with:

* Unigrams + Bigrams
* Maximum 100,000 features
* `min_df = 2`
* `sublinear_tf = True`
* L2 normalization

Final feature matrix:

```text
Training: 263,973 × 100,000
Testing : 65,994 × 100,000
```

---

## 🤖 Models

Two classical machine learning models were evaluated.

### 1. Logistic Regression

Used as the baseline classifier.

### 2. Linear SVM

Used as the advanced linear classifier.

Linear SVM achieved the best overall performance and was selected as the final model.

---

## 🏆 Results

### Final Linear SVM Performance

| Metric    |      Score |
| --------- | ---------: |
| Accuracy  | **91.42%** |
| Precision | **91.49%** |
| Recall    | **91.55%** |
| F1 Score  | **91.52%** |

### Baseline Comparison

| Model               |   Accuracy |  Precision |     Recall |         F1 |
| ------------------- | ---------: | ---------: | ---------: | ---------: |
| Logistic Regression |     91.36% |     91.40% |     91.53% |     91.46% |
| **Linear SVM**      | **91.42%** | **91.49%** | **91.55%** | **91.52%** |

---

## 🔍 Error Analysis

The final model still produces some classification errors.

Common challenging cases include:

* Sarcasm and irony
* Mixed positive and negative sentiment
* Negation
* Long contextual reviews
* Domain-specific language
* Noisy or translated text
* Reviews where sentiment depends heavily on context

The Linear SVM produced **5,703 incorrect predictions** on the test set.

---

## 🌐 Browser-Based Deployment

Instead of requiring a Python backend, the trained model parameters were exported into a browser-compatible JSON representation.

The deployment contains:

```text
deployment/
├── index.html
└── model.json
```

The browser performs:

```text
Text
 ↓
Arabic Cleaning
 ↓
Tokenization
 ↓
Unigrams + Bigrams
 ↓
Sublinear TF
 ↓
IDF
 ↓
L2 Normalization
 ↓
Linear SVM
 ↓
Positive / Negative
```

### Deployment Validation

The browser implementation was explicitly validated against the original Scikit-learn implementation.

Validation included:

* Vocabulary matching
* Feature count matching
* IDF matching
* SVM coefficient matching
* Intercept matching
* TF-IDF calculation
* L2 normalization
* SVM decision scores
* Final predictions

The browser and Scikit-learn predictions produced matching results on the validation examples.

---

## 🛠️ Technologies

* Python
* Scikit-learn
* Pandas
* NumPy
* Matplotlib
* Jupyter / Kaggle Notebooks
* JavaScript
* HTML
* CSS
* Hugging Face Spaces
* GitHub

---

## 📁 Repository Structure

```text
ArabicSentimentLens/
│
├── README.md
├── ArabicSentimentLens.ipynb
│
└── deployment/
    ├── index.html
    └── model.json
```

---

## 🔮 Future Improvements

Possible improvements include:

* Arabic transformer models such as AraBERT
* Fine-tuned multilingual transformers
* Better Arabic tokenization
* Handling sarcasm and negation
* Aspect-based sentiment analysis
* Multi-class sentiment classification
* Confidence calibration
* Larger and more diverse Arabic datasets

---

## 👨‍💻 Author

**Abdelrahman Mohamed (Boda)**

Computer Science & AI Student
Data Science Specialization

GitHub:
https://github.com/Boda-25

---

## ⭐ Project Links

🌐 **Live Demo:**
https://huggingface.co/spaces/abddoredaa222/ArabicSentimentLens

📓 **Kaggle Notebook:**
https://www.kaggle.com/code/arbhdmoa22/arabicsentimentlens

💻 **GitHub Repository:**
https://github.com/Boda-25/ArabicSentimentLens
