# PhD Coding Challenge: Loan Approval Automation Exploration

## Introduction

The coding part of this challenge is not necessarily wholly representative of the coding you will be doing within the research position. The type of question and context surrounding it, is however highly relevant to the envisioned content of the research. Especially how companies' implementation of these technologies impact society and what role regulation plays in mitigating these impacts. This challenge is purely designed to gauge how you can creatively solve questions by playing with economic intuition, definitions, data, and fundamental coding skills.

We are not looking for a specific or perfect solution, we just want to gauge your coding skills and thinking. For this reason the challenge is quite vague since it is more important to us to see what you come up with than to replicate what we think might be a good answer. You should therefore also not spend more than a day on this project. Submit your solution to your own branch on the [Prometis Lab GitHub project](https://github.com/PrometisLab/coding-challenge-data-gov-fintech).

## Challenge Overview

### Background

Prometis Bank has been processing loan applications manually through loan officers for several years. The bank is now considering implementing a model to automate the loan approval/rejection process to increase efficiency and consistency.

The bank has collected historical data of loan outcomes from previously approved applications. Each record includes anonymized borrower information, loan characteristics, and whether the loan was successfully repaid or defaulted.

### Task
Your task is to explore the feasibility and considerations of using automated models to assist in the loan approval/rejection process at Prometis Bank. Based on the historical data of previously approved loans, develop a predictive model. Your exploration must critically consider:
- **Predictive performance** of the model
- **Compliance requirements**, particularly those outlined in the EU AI Act for high-risk systems
- **Suitability and limitations** of the provided data for this task

## Submission Instructions

1. **Document your thinking** throughout the process
2. **Implement a basic solution** in Python and push it to your own branch on the [Prometis Lab GitHub repository](https://github.com/PrometisLab/coding-challenge-data-gov-fintech)
3. If time constraints prevent a complete solution, you may include **pseudo-code or text explanations** that detail:
   - What you would implement with additional time
   - The logical and code-based approach you would take
   - Expected outputs and results
4. **Prepare a concise report** (maximum 3 pages) communicating your approach and findings to the selection committee, which includes economists, finance professionals, and data scientists

## Dataset Description

### Overview

The dataset (`loan_dataset.csv`) contains historical records of 50,000 loans approved by Prometis Bank's loan officers between January 2020 and December 2022. Each record includes anonymized borrower information, loan characteristics, and the outcome (repaid or defaulted).

This data represents loans that were manually approved and then tracked to completion, serving as the foundation for developing your automation model.

### Dataset Structure

#### File Format
- CSV file with 50,000 rows and 19 columns
- No missing values
- Mixed numerical and categorical data

#### Features

| Feature Name | Type | Description |
|--------------|------|-------------|
| customer_id | Integer | Unique identifier for each customer |
| age | Integer | Age of the borrower (18-80) |
| income | Numeric | Annual income of the borrower in EUR |
| loan_amount | Numeric | Amount of loan in EUR |
| loan_term_months | Integer | Duration of the loan in months (12, 24, 36, 48, or 60) |
| credit_score | Integer | Credit score of the borrower (300-850) |
| employment_length_years | Numeric | Years of employment with current employer |
| debt_to_income_ratio | Numeric | Ratio of monthly debt payments to monthly income (0-0.6) |
| savings_amount | Numeric | Total savings amount in EUR |
| previous_defaults | Integer | Number of previous loan defaults (0-5) |
| education_level | Categorical | Highest education level achieved (high_school, bachelors, masters, phd) |
| zip_code_prefix | Categorical | First two digits of zip code (anonymized) |
| home_ownership | Categorical | Housing situation (rent, own, mortgage) |
| application_type | Categorical | How the application was submitted (online, in_person, phone) |
| loan_purpose | Categorical | Purpose of the loan (debt_consolidation, home_improvement, business, education, other) |
| has_cosigner | Binary | Whether the loan has a cosigner (0=no, 1=yes) |
| existing_customer | Binary | Whether the applicant was an existing customer (0=no, 1=yes) |
| application_date | Date | Date when the loan application was submitted (YYYY-MM-DD) |
| loan_status | Categorical | Target variable: final status of the loan (repaid, default) |

#### Derived Features

The dataset also includes two derived features calculated from the primary features:

| Feature Name | Type | Description |
|--------------|------|-------------|
| loan_to_income_ratio | Numeric | Ratio of loan amount to annual income |
| payment_to_income_ratio | Numeric | Ratio of estimated monthly payment to monthly income |

### Data Distribution

- Overall repayment rate: approximately 75%
- Loan amounts range from €1,000 to €100,000
- Loan terms range from 12 to 60 months
- Applications span from January 2020 to December 2022

### Important Notes

1. This dataset only contains loans that were initially **approved** by loan officers; it does not include rejected applications
2. All personally identifiable information has been removed or anonymized in compliance with GDPR
3. The zip code prefixes have been anonymized to two-digit codes that represent different geographic regions while preserving spatial patterns
4. No explicit protected attributes (such as gender, race, ethnicity) are included in the dataset
5. The data has already been cleaned—there are no missing values, duplicates, or obvious errors
6. The dataset is provided as-is with no additional preprocessing required to begin analysis

## EU AI Act Compliance Requirements

The following requirements apply to high-risk systems like credit scoring and should be addressed in your solution:

1. **Risk Management System**
   - Identify, analyze, and mitigate risks throughout the lifecycle
   - Test system effectiveness

2. **Data Governance**
   - Use high-quality, relevant, representative training/validation/testing data
   - Ensure data is free from errors and examined for possible issues
   - Implement appropriate data governance practices

3. **Technical Documentation**
   - Maintain detailed documentation on system design, methodologies, decisions, and assumptions

4. **Record-Keeping**
   - Log events and interventions automatically for oversight

5. **Transparency**
   - Provide clear information to users about purpose, limitations, decision processes, and risks

6. **Human Oversight**
   - Enable human review, intervention, or override ("human-in-the-loop"/"human-on-the-loop")

7. **Accuracy, Robustness, and Security**
   - Achieve appropriate accuracy levels
   - Ensure resilience to errors and manipulation
   - Implement proper security measures

8. **Non-discrimination and Fairness**
   - Design systems to avoid discriminatory outcomes
   - Implement safeguards, considering different population groups
   - Note: Even without explicit protected attributes, other variables can sometimes lead to discriminatory outcomes

## Deliverables

Your submission should include:

1. **Python Code**
   - Well-structured and commented implementation of your solution
   - Can be submitted as Jupyter Notebook(s) or Python scripts

2. **Analysis Report** (maximum 3 pages) including:
   - Analysis of the dataset: patterns, key relationships, and limitations regarding its origin and representativeness
   - Modeling approach, methodology, and evaluation of results, including performance across different data segments
   - Discussion of alignment with EU AI Act principles (data quality, robustness, human oversight, non-discrimination)
   - Assessment of potential operational challenges and considerations for responsible deployment
   - Evaluation of the dataset's limitations for building a real-world approval system
   - Clear recommendations for Prometis Bank, including potential next steps (data collection, model refinement, deployment considerations)

## Evaluation Criteria

Your submission will be evaluated based on:

1. **Economic reasoning and problem understanding**
2. **Technical implementation and coding skills**
3. **Compliance awareness and critical thinking**
4. **Communication and documentation quality**

Good luck with your submission! We look forward to seeing your  approach to this challenge.