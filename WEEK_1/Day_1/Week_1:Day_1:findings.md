# Week 1, Day 1: Data Exploration & Analysis

**Date:** June 5, 2026  
**Duration:** 50 minutes (20 min concept + 15 min code + 15 min reflection)  
**Focus:** What is Machine Learning? Load and explore audit data  

---

## 🎯 Today's Goal

✅ Understand what ML is  
✅ Load the UCI Audit Risk dataset  
✅ Explore key metrics and patterns  
✅ Identify surprising insights  

---

## 📊 Dataset Overview

**Source:** UCI Machine Learning Repository - Audit Risk Dataset  
**Origin:** India's Auditor Office (2015-2016)  
**Size:** 776 firm records | 18 features | Binary classification (High Risk / Low Risk)

### Key Metrics Found

```
Total Firms:           776
High-Risk Firms:       304
Low-Risk Firms:        472
High-Risk Percentage:  39.3%
```

---

## 🔍 Data Exploration Results

### Step 1: Data Shape
- Rows (firms): **776**
- Columns (features): **18**
- Data types: Mix of numeric and categorical

### Step 2: First 5 Rows
Loaded successfully in pandas using:
```python
df = pd.read_csv('audit_risk.csv')
df.head()
```

### Step 3: Summary Statistics
- Features include: financial ratios, audit history, compliance indicators
- Range of values varies widely across features
- Some features are binary (yes/no), others are continuous

### Step 4: Missing Data
- Checked with `df.isnull().sum()`
- Result: [FILL IN YOUR ACTUAL RESULT]

### Step 5: Target Variable Analysis

**Churn Distribution:**
```
Risk = 0 (Low Risk):   472 firms (60.7%)
Risk = 1 (High Risk):  304 firms (39.3%)
```

**Insight:** Class distribution is fairly balanced (~60/40), which is good for modeling.

---

## 💡 Key Observations & Surprises

### 1️⃣ The Big Surprise: 39.3% High-Risk

**Expected:** ~10% of firms to be flagged as high-risk  
**Found:** 39.3% are high-risk  
**Why?** This dataset represents India's Auditor Office auditing public sector firms in sectors like:
- Irrigation, Public Health, Agriculture, Corporate entities
- These sectors historically have higher control weaknesses
- Stricter audit standards apply to public sector auditing

**Audit Implication:** This isn't a data error — it's a genuinely risky population. This is exactly why scalable ML is critical: 39.3% of 776 = 304 firms need attention, but we can only sample ~50.

### 2️⃣ [ADD YOUR SECOND OBSERVATION HERE]

What else surprised you about the data?

### 3️⃣ [ADD YOUR THIRD OBSERVATION HERE]

What patterns did you notice?

---

## 📈 How This Connects to Scalable Audit

**Static Testing Problem:** Audit 50 firms → Hope they represent the 39.3% high-risk group  
**Scalable ML Solution:** Predict which of ALL 776 firms are truly high-risk → Test them all

This 39.3% metric will become the **target variable** for your Week 8 ML model.

---

## 🚀 What I Learned Today

1. **ML Concept:** ML finds patterns automatically instead of using manual rules
2. **Data Loading:** Pandas makes it easy to load, explore, and understand data
3. **Critical Thinking:** Always ask "Does this number make sense?" (39.3% surprised me because it was higher than expected)
4. **Business Context:** Same data means different things in different industries (39.3% is high but expected in public sector auditing)

---

## 📝 Reflection Questions

### Q1: Did the "What is ML?" concept make sense?
**Answer:** [YOUR ANSWER]

### Q2: What was the most surprising thing about the dataset?
**Answer:** 39.3% of firms are high-risk — 4x higher than my initial expectation of ~10%. This reflects the reality of public sector auditing.

### Q3: Which transformation excites you most?
**Answer:** Static → Scalable (testing 100% of firms continuously instead of sampling)

**Why:** I don't want to miss risky firms because we couldn't afford to test them. Continuous ML-powered testing means we catch all 304 high-risk firms, not just the ones in our sample.

---

## 🎯 Next Steps (Day 3)

- Learn **Supervised vs Unsupervised Learning**
- Understand how to predict the 39.3% high-risk firms
- Build intuition for classification problems

---

## 📌 Code Used Today

**Python Script:**
```python
import pandas as pd

# Load data
df = pd.read_csv('audit_risk.csv')

# Step 1: Shape
print(df.shape)  # Output: (776, 18)

# Step 2: First rows
print(df.head())

# Step 3: Summary stats
print(df.describe())

# Step 4: Missing values
print(df.isnull().sum())

# Step 5: Target analysis
print(df['Risk'].value_counts())
high_risk_pct = (df['Risk'].sum() / len(df)) * 100
print(f"High-risk: {high_risk_pct:.1f}%")  # Output: 39.3%
```

**Notebook:** `audit_data_exploration.ipynb`

---

## 🔗 Resources Used

- DeepLearning.AI: "Machine Learning for Everyone" intro video
- Google Colab: Free Jupyter notebook environment
- UCI ML Repository: Audit Risk Dataset
- Pandas documentation: Data exploration methods

---

## ✅ Day 1: COMPLETE

**Time Spent:** 50 minutes  
**Code Written:** 20 lines  
**Insights Gained:** 3+  
**Next Session:** Day 3 (Supervised vs Unsupervised Learning)

---

*"The intersection of audit, data engineering, analytics, and ML is becoming incredibly powerful." — My learning philosophy*
