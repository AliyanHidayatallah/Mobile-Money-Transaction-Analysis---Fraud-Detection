# Mobile Money Transaction Analysis - Fraud Detection

## Overview
This project involves analyzing a dataset of mobile money transactions to uncover trends, insights, and patterns related to fraud detection. The dataset contains multiple types of transactions and indicators of both flagged and confirmed fraudulent activity. The goal of the project is to better understand how fraud occurs within these transactions and to provide actionable insights that can help improve fraud detection mechanisms.

## Dataset
The dataset used in this analysis was a subset of the PaySim dataset, originally created to simulate mobile money transactions for fraud detection purposes. The dataset consists of five transaction types:
- **CASH-IN**: Deposits into an account
- **CASH-OUT**: Withdrawals from an account
- **DEBIT**: Bank transfers
- **PAYMENT**: Purchases of goods or services
- **TRANSFER**: User-to-user money transfers

Additionally, the dataset includes two columns related to fraud detection:
- **IsFlaggedFraud**: A binary column indicating whether a transaction was flagged by the system as potentially fraudulent.
- **IsFraud**: A binary column indicating confirmed fraud cases.

## Project Structure

### 1. Dataset Exploration
The first step in this project was to explore the dataset using Python libraries such as Pandas and Matplotlib. Key statistics about the dataset were generated, such as the frequency of each transaction type, the relationship between transaction types and fraud occurrences, and insights into flagged fraud cases.

**Key Findings:**
- CASH-OUT and PAYMENT transactions made up a significant portion of the dataset.
- TRANSFER transactions were the most frequent source of flagged fraud cases.
- A significant number of flagged fraud cases turned out to be false positives, highlighting the need for improvements in fraud detection algorithms.

### 2. Dataset Manipulation
The following exercises were completed to manipulate and query the dataset:

- **Exercise 0**: Read the dataset as a Pandas DataFrame.
- **Exercise 1**: Return the column names of the dataset.
- **Exercise 2**: Return the first *k* rows of the dataset.
- **Exercise 3**: Return a random sample of *k* rows from the dataset.
- **Exercise 4**: Return a list of unique transaction types.
- **Exercise 5**: Return the top 10 transaction destinations with their frequencies.
- **Exercise 6**: Return all rows where fraud was detected.
- **Bonus**: Return the number of distinct destinations each source interacted with, sorted in descending order.

### 3. Data Visualization
Several visualizations were created to better understand the dataset and the patterns of fraud detection:

#### 3.1 Transaction Types and Fraud Detection
The first visualization compares the frequency of transaction types, as well as their split by fraudulent vs. non-fraudulent transactions.

#### 3.2 Scatter Plot for Cash-Out Transactions
This scatter plot compares the origin account balance delta to the destination account balance delta for cash-out transactions, allowing a visual inspection of suspicious outliers.

### 4. Recommendations for Fraud Detection
Based on the analysis and visualizations, the following recommendations can be made to improve fraud detection:
- Focus manual reviews on **CASH-OUT** and **TRANSFER** transactions, as these are the most common fraud-prone transaction types.
- Improve the algorithm’s sensitivity to false positives by focusing on transaction amounts and timing, which were identified as key factors in fraud occurrences.

## Conclusion
This project provided valuable insights into the patterns of fraud within mobile money transactions. By analyzing transaction data and visualizing key metrics, I was able to recommend actionable steps to improve fraud detection, reduce false positives, and enhance security measures for financial services providers.

