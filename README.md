# Team-Project-2
# Creditworthiness and Risk Assessment: Identifying Factors Influencing Credit Scores and Loan Approval Outcomes

# Project Proposal: Creditworthiness Classification
## Objective
The aim of our project is to uncover patterns in customer creditworthiness to help predict their likelihood of repaying loans. We’ll examine relationships between factors such as income levels, payment behavior, credit mix, and debt ratios. Our goal is to use these variables to classify customers into categories based on their credit scores—Good, Standard, or Poor—using a machine learning model. This project has the potential to support financial institutions in making data-driven decisions on loan approvals, minimizing risk, and promoting financial accessibility.

## Questions:
1. How do various financial metrics and demographics correlate with credit scores?
2. What are the most influential factors impacting loan approval outcomes?
3. How have creditworthiness trends evolved over time?

## Project Overview
This project examines relationships between several factors affecting credit scores and loan approvals, including income, debt, employment stability, and past credit behavior. By identifying key patterns, we aim to uncover trends and insights into creditworthiness and the risk factors associated with loan defaults.

The project utilizes Python and employs libraries such as Pandas for data manipulation, Matplotlib for data visualization, and Scikit-learn for model analysis.

---

## Data Files
The project uses the following CSV data files located in the `Resources` folder:
1. `Credit_Scores.csv`: Historical data on credit scores.
2. `Loan_Approval_Records.csv`: Loan approval/rejection records.
3. `Financial_Stability.csv`: Metrics like income, debt-to-income ratio, and employment history.
4. `Demographic_Info.csv`: Information such as age, education, and occupation.

---

## Key Functions & Workflow

1. **Data Import and Preparation**
   - Import datasets using Pandas, filtering for relevant variables.
   - Clean and preprocess data by handling missing values and standardizing formats.

2. **Credit Score Analysis**
   - Filter credit score data to focus on the relevant time period (e.g., 2015-2024).
   - Create monthly and annual averages to track trends in credit scores.

3. **Data Merging**
   - Merge datasets on common fields such as `ClientID` and `Date` to facilitate a comprehensive analysis of credit scores, loan outcomes, and influencing factors.

4. **Data Visualization**
   - Generate visualizations to highlight patterns across demographics, income, and loan approval rates. Visualizations are saved in the **Graphs** folder:
     - Credit Score Trends Over Time
     - Loan Approval Rates by Income Level
     - Debt-to-Income Ratio vs. Credit Score

5. **Correlation Analysis**
   - Compute correlations between credit score and metrics like income, debt, and loan status, with findings such as:
     - Positive correlation between stable income and higher credit scores.
     - Inverse correlation between high debt-to-income ratio and loan approval likelihood.

6. **Predictive Analysis**
   - Utilize machine learning models to predict loan approval likelihood based on creditworthiness factors.

---

# Examples and Outputs

## Output
The code produces:
1. **Graphs**: Visualizations in the `Graphs` folder:
   - Credit Score Trends Over Time
   - Loan Approval Rates by Income Level
   - Debt-to-Income Ratio vs. Credit Score

2. **Correlation Analysis**: Printed correlation values to understand relationships between metrics.

## Examples
1. **Plot Credit Score Trends Over Time:**

   ```python
   # Plotting average credit scores over time
   credit_scores['Date'] = pd.to_datetime(credit_scores['Date'])
   avg_scores = credit_scores.groupby(credit_scores['Date'].dt.year)['Credit_Score'].mean()

   plt.figure(figsize=(10, 6))
   plt.plot(avg_scores.index, avg_scores.values, color='purple', label='Average Credit Score')
   plt.xlabel('Year')
   plt.ylabel('Average Credit Score')
   plt.title('Average Credit Score Trends Over Time')
   plt.legend()
   plt.savefig('Graphs/CreditScoreTrend.png', dpi=300, bbox_inches='tight')
   plt.show()
