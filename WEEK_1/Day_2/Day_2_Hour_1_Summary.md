# Week 1, Day 2: Hour 1 Learning Summary
## Supervised vs Unsupervised Learning

**Date:** [Today's Date]  
**Duration:** 60 minutes  
**Focus:** Understanding the two fundamental approaches to machine learning  
**Status:** ✅ COMPLETE  

---

## 🎯 What I Learned

### **The Core Difference**

Machine Learning splits into two main branches based on whether you have **labeled data** (answers) or not:

**SUPERVISED LEARNING:** You have the answers
- **Data:** Labeled pairs (Input → Output, Feature → Label)
- **Goal:** Train on past examples, then predict outcomes for new data
- **Evaluation:** Easy to measure accuracy (compare predictions to actual labels)
- **Complexity:** High human effort upfront (labeling data), but computationally simple
- **Common Use:** Classification, Regression, Prediction

**UNSUPERVISED LEARNING:** You discover the answers
- **Data:** Unlabeled items (only inputs, no labels)
- **Goal:** Find hidden patterns, groups, or structures in data
- **Evaluation:** Subjective (no "correct answer" to compare against)
- **Complexity:** Less human prep work, but more computationally intensive
- **Common Use:** Clustering, Anomaly Detection, Dimensionality Reduction

---

## 📊 My Two Audit Examples

### **Example 1: SUPERVISED LEARNING — Revenue Testing**

**Problem:** Predict which revenue transactions are potentially misstated or high-risk.

**Historical Data (Training Set):**
- Past 500+ revenue transactions, each labeled:
  - Valid
  - High-risk
  - Incorrectly recognized
  - Unsupported
  - Cutoff exceptions

**Features the Model Learns From:**
- Transaction date and posting period
- Revenue amount
- Customer type
- Manual journal adjustments
- End-of-quarter transactions
- Discounts or unusual pricing
- Shipping date vs invoice date
- Credit memo activity
- Sales region
- Product category

**Patterns the Model Would Learn:**
- Large transactions posted near quarter-end = higher risk
- Unusual spikes in sales activity = suspicious
- Revenue recognized before shipment = potential fraud
- Excessive discounts = risk flag
- Abnormal customer behavior = watch closely

**Application in Audit:**
- Prioritize which revenue transactions to test
- Improve revenue cutoff testing efficiency
- Detect potential revenue manipulation automatically
- Reduce manual sampling (test the highest-risk items, not random ones)
- Enhance fraud detection

**Success Metric:** Accuracy — "My model correctly identifies 88% of misstated transactions"

---

### **Example 2: UNSUPERVISED LEARNING — Operating Expense Testing**

**Problem:** Discover hidden patterns and anomalies in operating expenses WITHOUT pre-defining what "suspicious" means.

**Raw Data (No Labels):**
- All 50,000 operating expense records from the year
- Expense reports, vendor payments, reimbursement transactions, procurement data
- **NO labels** (we don't know in advance which ones are "problematic")

**What the Model Discovers:**
- Clusters of similar spending behavior
  - Normal expense cluster: ~49,500 transactions following typical patterns
  - Unusual cluster: ~450 transactions with odd combinations
    - Very high amounts paired with unusual GL accounts
    - Round numbers with multiple approvers
    - Off-cycle entries with senior management approval

- Vendor patterns
  - Normal vendors: regular payment schedules, typical amounts
  - Suspicious vendors: irregular payments, sudden spikes

- Department anomalies
  - Some departments' expenses don't match historical patterns
  - Unusual spending seasonality

**Application in Audit:**
- Review the 450 unusual expenses instead of all 50,000 (targeted testing)
- Detect emerging fraud risks proactively
- Identify suspicious vendor relationships
- Improve spend analytics and operational efficiency
- Support internal audit investigations

**Success Metric:** Subjective — "Did we find real, actionable patterns? Were the flagged expenses actually problematic?" Requires manual validation.

---

## 🔑 Key Insights

### **Why This Matters for Your Career**

Both approaches are critical:
- **Supervised Learning** = You're predicting something specific (Will this transaction be misstated? Will this client default?)
- **Unsupervised Learning** = You're exploring something unknown (What unusual patterns exist in this expense data?)

In audit, you'll need BOTH:
- Supervised for: Client risk classification, transaction risk scoring, control failure prediction
- Unsupervised for: Anomaly detection, fraud discovery, finding patterns auditors didn't think to look for

### **Connection to Your Audit Data**

Your 776 firms + 39.3% high-risk finding is a PERFECT supervised learning setup:
- You have 304 high-risk firms (Label = 1)
- You have 472 low-risk firms (Label = 0)
- A supervised model would learn: "What features separate the high-risk group from the low-risk group?"
- Then it could predict: "For this NEW firm, is it likely high-risk or low-risk?"

In Hour 2, you'll explore exactly this question with code.

---

## 📚 Videos Watched

1. DeepLearning.AI: Supervised Learning Part 1
2. DeepLearning.AI: Supervised Learning Part 2
3. DeepLearning.AI: Unsupervised Learning Part 1
4. DeepLearning.AI: Unsupervised Learning Part 2

**Note:** StatQuest link provided was broken. Alternative: YouTube search "supervised vs unsupervised learning" for similar quality explanations.

---

## 🎓 Concepts Mastered

- ✅ Definition of supervised learning
- ✅ Definition of unsupervised learning
- ✅ Difference between labeled and unlabeled data
- ✅ Why labeling matters (cost/benefit tradeoff)
- ✅ How evaluation differs between the two
- ✅ Real audit examples for each approach
- ✅ Connection to your current audit work

---

## ❓ Questions Still Exploring

1. Which algorithms are best for each approach? (Answer coming in Week 2)
2. How do I know when to use supervised vs unsupervised? (Context-dependent; will learn through practice)
3. Can I combine both approaches? (Yes—semi-supervised learning is a thing)

---

## 🚀 Next Steps (Hour 2)

- **Code:** Load audit data and explore which features predict high-risk firms
- **Analysis:** Create visualizations showing differences between high-risk and low-risk groups
- **Insight:** Document patterns that a supervised model WOULD learn
- **GitHub:** Commit findings and analysis

**Hour 1 Status:** ✅ Complete  
**Ready for Hour 2:** ✅ Yes
