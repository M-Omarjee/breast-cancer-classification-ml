# breast-cancer-classification-ml
Breast cancer classification (malignant vs benign) using Logistic Regression and Random Forest, with clinical insights.
# 🩺 Breast Cancer Classification (Logistic Regression vs Random Forest)

This project explores the **Breast Cancer Wisconsin dataset** (built into scikit-learn) to predict whether a tumour is **malignant** or **benign** based on features like cell radius, texture, concavity, and symmetry.

I trained and compared two models:
- **Logistic Regression**
- **Random Forest**

---

## 🔑 Results (Test Set)

| Model               | Accuracy | Recall (Malignant) | Precision (Malignant) | AUC   |
|---------------------|----------|---------------------|------------------------|-------|
| Logistic Regression | **98.2%** | **0.98**            | 0.98                   | 0.995 |
| Random Forest       | 95.6%    | 0.93                 | 0.95                   | 0.993 |

---

## 📊 Key Insights
- Logistic Regression slightly outperformed Random Forest.  
- **Recall for malignant cases was 0.98** with Logistic Regression (it only missed 1 malignant tumour out of 42).  
- Random Forest achieved strong accuracy but missed more malignant cases (recall 0.93).  
- In a healthcare context, **catching malignant cases is critical**, so Logistic Regression is the better choice here.  

---

## 🖼️ Visuals

### Confusion Matrices
**Logistic Regression** (left) vs **Random Forest** (right)  
- Logistic Regression misclassified 1 malignant + 1 benign.  
- Random Forest misclassified 3 malignant + 2 benign.  

![Confusion Matrix](confusion_matrix_logreg.png) ![Confusion Matrix](confusion_matrix_rf.png)

---

### ROC Curve (Test Set)
Both models show near-perfect separation, with AUC values above 0.99.

![ROC Curve](breast_cancer_roc.png)

---

### Feature Importance
Logistic Regression coefficients show that **worst texture, radius error, concave points, and tumour size measures** were the strongest predictors of malignancy — which makes sense clinically, since irregular growth patterns are a red flag.

![Feature Importance](logreg_feature_importance.png)

---

## ⚙️ How to Run

1. Clone the repo or open in Google Colab.  
2. Install dependencies:
   ```bash
   pip install scikit-learn pandas matplotlib seaborn
