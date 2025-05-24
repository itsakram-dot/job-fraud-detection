# Job‑Fraud Detection for Recruiting Platforms

## 1 Overview
Recruiting sites lose money and user trust when fake job ads harvest personal data or fees.  
This project builds a lightweight text‑analytics pipeline that flags suspicious listings in real time so Trust & Safety teams can review them first.

## 2 Business Case
* **Annual liability** (baseline): about \$5 M in victim remediation costs.   
* **Model catch rate:** 78 % of scams at a 4 % false‑alarm rate.  
* **Savings if fraud is cut in half:** ≈ \$2.55 M each year; review overhead is under \$20 k, giving a 128× return on investment.

## 3 Data
Kaggle “Real or Fake Job Postings” (≈ 18 k ads; 89 % real, 11 % fake).  
Fields include title, company profile, description, and requirements.

## 4 Method
1. **Clean & feature‑engineer**  
   * text lengths, logo flag, telecommute flag  
2. **Model**  
   * TF‑IDF (unigrams + bigrams, 10 k terms)  
   * Logistic Regression with balanced class weights  
3. **Explainability**  
   * SHAP waterfall plots show why any listing is flagged

## 5 Key Results
| Metric | Value |
|--------|-------|
| Accuracy | 0.96 |
| Precision (fraud) | 0.85 |
| Recall (fraud) | 0.78 |
| ROC‑AUC | 0.97 |

Lowering the threshold to 0.30 raises recall to 0.90 while keeping ROI above 48×.  

## 6 How to Run
```bash
# clone repo and create env
git clone
cd job‑fraud‑detector
conda env create -f environment.yml
conda activate fraud‑env
