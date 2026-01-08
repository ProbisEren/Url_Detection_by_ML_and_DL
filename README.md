# Phishing URL Detection using Machine Learning and Deep Learning

A comprehensive machine learning project for detecting phishing URLs using multiple algorithms including Logistic Regression, Linear SVM, Random Forest, and LSTM.

## 📊 Project Overview

This project implements and compares 4 different machine learning approaches to detect phishing URLs with over 99% accuracy. The system analyzes URL patterns using character-level features to distinguish malicious from legitimate websites.

**Course:** Learning from Data  
**Institution:** FSMVÜ  
**Date:** January 2026

## 🎯 Key Results

| Model | Accuracy | Training Time | Best For |
|-------|----------|---------------|----------|
| **Linear SVM** | **99.92%** | 1.61s | Best overall performance |
| **LSTM** | 99.65% | 360s | Deep learning approach |
| **Logistic Regression** | 99.29% | 0.19s | Real-time deployment |
| Random Forest | 96.59% | 0.60s | Feature importance |

## 📁 Project Structure
```
URL_Detection_by_ML_and_DL/
├── url_detection.ipynb          # Complete implementation
├── requirements.txt              # Python dependencies
├── README.md                     # This file
├── data/
│   ├── raw/                      # Original collected data
│   │   ├── phishing_urls.json    # PhishTank data (46,166 URLs)
│   │   └── legit_urls.json       # Tranco data (50,000 URLs)
│   └── processed/                # Train/val/test splits
│       ├── train.csv             # 67,316 samples
│       ├── val.csv               # 14,425 samples
│       └── test.csv              # 14,425 samples
├── outputs/
│   └── figures/                  # All visualizations
│       ├── *_confusion_matrix.png
│       ├── *_roc_curve.png
│       └── learning_curve_*.png
└── models/                       # (Optional) Saved models
```

## 🔧 Installation

### Prerequisites
- Python 3.11+
- pip package manager

### Setup

1. **Clone the repository**
```bash
git clone https://github.com/ProbisEren/Url_Detection_by_ML_and_DL.git
cd Url_Detection_by_ML_and_DL
```

2. **Create virtual environment** (recommended)
```bash
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

## 🚀 Usage

### Running the Notebook

1. **Start Jupyter Notebook**
```bash
jupyter notebook url_detection.ipynb
```

2. **Run all cells** in order (Runtime → Run All)

### Quick Start
```python
# Load the notebook and run sections:
# 1. Data Collection (Section 2)
# 2. Preprocessing (Section 2)
# 3. Feature Engineering (Section 3.1)
# 4. Model Training (Section 3.2-3.3)
# 5. Evaluation (Section 4)
```

## 📊 Dataset

**Total URLs:** 92,332 (perfectly balanced)
- **Phishing URLs:** 46,166 from [PhishTank](https://www.phishtank.com/)
- **Legitimate URLs:** 46,166 from Tranco list & Google top domains

**Split:** 70% Train, 15% Validation, 15% Test

### Data Collection

Data was collected using:
- **PhishTank API:** Verified phishing URLs (JSON endpoint)
- **Tranco List:** Top legitimate websites (research-grade ranking)

All data collection follows respective Terms of Service and ethical guidelines.

## 🧠 Methodology

### Feature Engineering
1. **Bag-of-Words (BoW)** - Character n-grams (2-4)
2. **TF-IDF** - Weighted character n-grams
3. **Custom Features** - URL length, digit count, special chars, HTTPS, IP detection
4. **Character Sequences** - For LSTM (max length: 200)

### Models Implemented

#### Traditional ML
- **Logistic Regression** - Linear classifier with L2 regularization
- **Linear SVM** - Maximum margin classifier (best performance)
- **Random Forest** - Ensemble of 200 decision trees

#### Deep Learning
- **LSTM** - Recurrent neural network with dropout regularization

### Training Strategy
- **Cross-Validation:** 5-fold stratified
- **Hyperparameter Tuning:** GridSearchCV (Random Forest)
- **Regularization:** L2, Dropout (0.3), Early Stopping (patience=3)

## 📈 Results

### Performance Metrics

**Linear SVM (Best Model):**
- Accuracy: 99.92%
- Precision: 99.97%
- Recall: 99.87%
- F1-Score: 99.92%
- AUC-ROC: 0.9998

**All Visualizations:** Available in `outputs/figures/`
- Confusion matrices for all 4 models
- ROC curves with AUC scores
- Learning curves showing convergence
- Model comparison charts

### Key Findings
- ✅ Character n-grams (5000 features) >> Hand-crafted features (5 features)
- ✅ Linear SVM optimal for this task (99.92% accuracy in 1.61s)
- ✅ Minimal preprocessing preserves informative URL patterns
- ✅ No overfitting (small train-test gap, consistent CV results)

## 🛠️ Technologies Used

- **Python 3.11**
- **scikit-learn** - ML algorithms, evaluation metrics
- **TensorFlow/Keras** - LSTM implementation
- **pandas** - Data manipulation
- **matplotlib** - Visualizations
- **requests** - API data collection

## 📖 Report

Complete project report (11 pages) available: `Phishing_URL_Detection_Report.pdf`

Includes:
- Problem motivation and objectives
- Data collection methodology
- Feature engineering approaches
- Comprehensive model comparison
- Learning curves and bias-variance analysis
- Error analysis with examples
- Computational analysis

## 👥 Team Members

- **Metin Eren Uzun** - 2221251009
- **Gamze Partal** - 2221251035
- **Şule Yücel** - 2221251005

## 📚 References

1. PhishTank. "Join the fight against phishing." https://www.phishtank.com/
2. Le Pochat et al. "Tranco: A Research-Oriented Top Sites Ranking." NDSS 2019.
3. Pedregosa et al. "Scikit-learn: Machine Learning in Python." JMLR 12, 2011.
4. Chollet, François. "Keras." https://keras.io, 2015.

## 📝 License

This project is for academic purposes as part of the "Learning from Data" course.

## 🙏 Acknowledgments

- **Instructor:** Cumali Türkmenoğlu
- **Data Sources:** PhishTank community, Tranco project
- **Course:** Learning from Data

---

**⭐ Star this repo if you find it helpful!**

For questions or issues, please open an issue on GitHub.