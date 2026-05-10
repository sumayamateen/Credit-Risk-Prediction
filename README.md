# 🏦 Credit Risk Exploratory Data Analysis (EDA)

> Comprehensive analysis of 307,511 loan applications to uncover default patterns and risk factors

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/Pandas-Data_Analysis-green.svg)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

---

## 📊 Project Overview

This project performs in-depth exploratory data analysis on the **Home Credit Default Risk** dataset to understand:
- What factors contribute to loan defaults?
- Which customer segments have higher risk?
- How do demographic and financial variables relate to repayment behavior?

**Business Context:** Banks lose billions annually from loan defaults. Understanding default patterns is the first step toward building predictive models that reduce risk.

---

## 🎯 Key Findings

### Default Rate
- **Overall Default Rate:** 8.07% (24,825 defaults out of 307,511 applications)
- This means approximately 1 in 12 customers fail to repay their loans

### Critical Risk Factors Discovered

| Factor | Key Insight | Business Impact |
|--------|-------------|-----------------|
| **Age** | Younger applicants have significantly higher risk (18-25: 12.30% vs 65-75: 3.73%) | Implement age-based approval criteria |
| **External Credit Score** | Weak negative correlation with default (-0.16 to -0.18); best predictor among available features | Use as supporting factor, not sole decision driver |
| **Employment Duration** | Longer employment = lower default risk (<1 year: 10.97% vs 10+ years: 5.19%) | Require minimum employment tenure |
| **Income Level** | Mixed pattern; medium income (100k-200k) shows highest default (8.55%) | Use with other factors, not alone |
| **Gender** | Males have higher default rate (10.14% vs females 7.00%) | Consider gender in risk models |
| **Car Ownership** | Car owners default less (7.24% vs 8.50%) | Use as supporting risk indicator |
| **Homeownership** | Homeowners have slightly lower default (7.96% vs renters 8.32%) | Consider housing stability |
| **Children** | 4 children shows highest risk (12.82%), but sample size small | Use with caution |

---

## 📂 Dataset Information

**Source:** [Home Credit Default Risk (Kaggle)](https://www.kaggle.com/c/home-credit-default-risk/data)

**Size:**
- **Rows:** 307,511 loan applications
- **Columns:** 122 features
- **Target Variable:** Binary (0 = Repaid, 1 = Default)

**Feature Categories:**
- Demographics (age, gender, family status)
- Financial (income, credit amount, annuity)
- Employment (occupation, years employed)
- Assets (car ownership, property ownership)
- Credit Bureau (external scores, credit inquiries)
- Application (contract type, weekday, hour)
- Documents (21 document submission flags)

---

## 🔍 Analysis Performed

### 1. **Data Understanding**
- Dataset shape and structure
- Data types and column overview
- Statistical summary of numerical features
- Missing value analysis

### 2. **Default Rate Analysis**
- Overall default rate calculation
- Default distribution visualization

### 3. **Demographic Analysis**
✅ **Children vs Default**
- How number of children affects default probability
- Family size impact on repayment behavior

✅ **Single Parents Analysis**
- Default rates among single parents
- Financial stress indicators

✅ **Age vs Default**
- Age group segmentation
- Risk profiles by age bracket

✅ **Family Members vs Default**
- Household size correlation with default
- Living situation impact

✅ **Gender vs Default**
- Male vs female default rates
- Gender-based risk differences

### 4. **Financial Analysis**
✅ **Income vs Default**
- Income brackets and default correlation
- Income-to-loan ratio analysis

✅ **External Credit Scores**
- External source 1, 2, 3 correlation with default
- Credit score predictive power

### 5. **Employment Analysis**
✅ **Employment vs Default**
- Employment duration and stability
- Occupation type risk profiles

### 6. **Asset Analysis**
✅ **Housing Type vs Default**
- House ownership vs renting patterns
- Housing stability indicator

✅ **Car Ownership vs Default**
- Car owners vs non-owners default rates
- Asset ownership as risk signal

### 7. **Data Quality Assessment**
- Missing value patterns
- Data integrity checks
- Outlier identification

---

## 📈 Visualizations

The notebook includes multiple visualizations:
- Distribution plots for key variables
- Bar charts comparing default rates across categories
- Correlation heatmaps
- Box plots for outlier detection
- Count plots for categorical variables

---

## 🛠️ Technologies Used

**Languages & Libraries:**
- **Python 3.8+**
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical data visualization

**Environment:**
- **Jupyter Notebook** - Interactive analysis

---

## 🚀 How to Run This Analysis

### Prerequisites
```bash
# Ensure you have Python 3.8 or higher installed
python --version
```

### Installation

1. **Clone the repository**
```bash
git clone https://github.com/sumayamateen/credit-risk-prediction.git
cd credit-risk-prediction
```

2. **Install required packages**
```bash
pip install pandas numpy matplotlib seaborn jupyter
```

3. **Download the dataset**
- Download `application_train.csv` from [Kaggle](https://www.kaggle.com/c/home-credit-default-risk/data)
- Place it in the project directory

4. **Run the notebook**
```bash
jupyter notebook 01_EDA_Data_Exploration.ipynb
```

---

## 📊 Sample Insights

### Example Finding: Income vs Default

```python
# Code snippet from analysis
default_rate = df["TARGET"].sum() / len(df) * 100
print(f"Default rate: {default_rate:.2f}%")
# Output: Default rate: 8.07%
```

### Statistical Summary

The analysis reveals:
- Average loan amount: 599,026 currency units
- Average income: 168,798 currency units
- Loan-to-income ratio varies significantly across defaulters vs non-defaulters

---

## 💡 Business Recommendations

Based on the EDA findings:

1. **Risk Segmentation**
   - Create low/medium/high risk categories based on discovered patterns
   - Adjust approval thresholds for each segment

2. **Feature Importance**
   - Prioritize external credit scores in decision-making
   - Consider income-to-loan ratio as primary metric
   - Factor in employment stability

3. **Data Quality**
   - Address missing values in critical fields (external scores, occupation)
   - Implement better data collection for high-impact features

4. **Next Steps**
   - Build predictive models using identified risk factors
   - Develop automated risk scoring system
   - Create monitoring dashboard for portfolio health

---

## 📁 Project Structure

```
credit-risk-prediction/
│
├── 01_EDA_Data_Exploration.ipynb    # Main analysis notebook
├── README.md                         # This file
├── requirements.txt                  # Python dependencies
│
└── data/
    └── application_train.csv         # Dataset (not included - download from Kaggle)
```

---

## 🔮 Future Work

- [ ] Deep dive into missing value patterns
- [ ] Feature engineering for predictive modeling
- [ ] Advanced visualizations (interactive dashboards)
- [ ] Correlation analysis with external data sources
- [ ] Build machine learning models based on insights
- [ ] Create Power BI dashboard for stakeholders

---

## 📚 Key Takeaways

### For Data Scientists:
- Demonstrates systematic EDA approach
- Shows how to handle large datasets (300K+ rows)
- Exhibits feature analysis techniques
- Prepares groundwork for predictive modeling

### For Business Stakeholders:
- Identifies 8.07% default rate as key metric
- Highlights critical risk factors for decision-making
- Provides actionable insights for risk management
- Quantifies patterns in customer behavior

---

## 👤 Author

**Sumaya Mateen**  
Data Analyst | Python, SQL, Power BI

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-blue)](https://www.linkedin.com/in/sumaya-mateen)
[![Email](https://img.shields.io/badge/Email-Contact-red)](mailto:sumayamateen6@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-View-green)](https://github.com/sumayamateen/Analytics-Portfolio)

---

## 🙏 Acknowledgments

- **Dataset:** [Home Credit Group](https://www.kaggle.com/c/home-credit-default-risk) via Kaggle
- **Inspiration:** Kaggle community notebooks and discussions
- **Tools:** Python data science ecosystem

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 📝 Notes

**Currency:** The dataset does not specify currency. Values are likely in Czech Koruna (CZK) or normalized units from Home Credit Group's international operations.

**Data Privacy:** All data is anonymized. No personally identifiable information (PII) is included.

**Reproducibility:** Results are reproducible by running the notebook with the same dataset version.

---

⭐ **If you found this analysis useful, please star this repository!**

---

*Last Updated: May 2026*
