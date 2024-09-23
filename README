# Mobile Money Transaction Analysis - Fraud Detection

## Overview

This project involves analyzing a dataset of mobile money transactions to uncover trends, insights, and patterns related to fraud detection. The dataset contains multiple types of transactions and indicators of both flagged and confirmed fraudulent activity. The goal of the project is to better understand how fraud occurs within these transactions and to provide actionable insights that can help improve fraud detection mechanisms.

## Dataset

The dataset used in this analysis was a subset of the *PaySim* dataset, originally created to simulate mobile money transactions for fraud detection purposes. The dataset consists of five transaction types:

- **CASH-IN**: Deposits into an account
- **CASH-OUT**: Withdrawals from an account
- **DEBIT**: Bank transfers
- **PAYMENT**: Purchases of goods or services
- **TRANSFER**: User-to-user money transfers

Additionally, the dataset includes two columns related to fraud detection:

- **IsFlaggedFraud**: A binary column indicating whether a transaction was flagged by the system as potentially fraudulent.
- **IsFraud**: A binary column indicating confirmed fraud cases.

The dataset can be downloaded from the [PaySim Kaggle page](https://www.kaggle.com/ealaxi/paysim1/version/2).

## Project Structure

### 1. Dataset Exploration

The first step in this project was to explore the dataset using Python libraries such as Pandas and Matplotlib. Key statistics about the dataset were generated, such as the frequency of each transaction type, the relationship between transaction types and fraud occurrences, and insights into flagged fraud cases.

#### Key Findings:
- **CASH-OUT** and **PAYMENT** transactions made up a significant portion of the dataset.
- **TRANSFER** transactions were the most frequent source of flagged fraud cases.
- A significant number of flagged fraud cases turned out to be false positives, highlighting the need for improvements in fraud detection algorithms.

### 2. Dataset Manipulation

The following exercises were completed to manipulate and query the dataset:

- **Exercise 0**: Read the dataset as a Pandas DataFrame.
- **Exercise 1**: Return the column names of the dataset.
- **Exercise 2**: Return the first `k` rows of the dataset.
- **Exercise 3**: Return a random sample of `k` rows from the dataset.
- **Exercise 4**: Return a list of unique transaction types.
- **Exercise 5**: Return the top 10 transaction destinations with their frequencies.
- **Exercise 6**: Return all rows where fraud was detected.
- **Bonus**: Return the number of distinct destinations each source interacted with, sorted in descending order.

### 3. Data Visualization

Several visualizations were created to better understand the dataset and the patterns of fraud detection:

#### 3.1 Transaction Types and Fraud Detection

The first visualization compares the frequency of transaction types, as well as their split by fraudulent vs. non-fraudulent transactions.

```python
def visual_1(df):
    def transaction_counts(df):
        return df['type'].value_counts()
    def transaction_counts_split_by_fraud(df):
        return df.groupby(by=['type', 'isFraud']).size()

    fig, axs = plt.subplots(2, figsize=(6,10))
    transaction_counts(df).plot(ax=axs[0], kind='bar')
    axs[0].set_title('Transaction Types Frequencies')
    axs[0].set_xlabel('Transaction Type')
    axs[0].set_ylabel('Occurrence')
    transaction_counts_split_by_fraud(df).plot(ax=axs[1], kind='bar')
    axs[1].set_title('Transaction Types Frequencies, Split by Fraud')
    axs[1].set_xlabel('Transaction Type, Fraud')
    axs[1].set_ylabel('Occurrence')
    fig.suptitle('Transaction Types')
    fig.tight_layout(rect=[0, 0.03, 1, 0.95])
    for ax in axs:
      for p in ax.patches:
          ax.annotate(p.get_height(), (p.get_x(), p.get_height()))
    return 'While the transaction frequencies depend on the available data, an interesting insight here is that fraudulent activity is only seen on CASH_OUT and TRANSFER transactions. This can inform management to focus the effort of manual reviews on these transaction types to reduce fraud.'

3.2 Scatter Plot for Cash-Out Transactions

This scatter plot compares the origin account balance delta to the destination account balance delta for cash-out transactions, allowing a visual inspection of suspicious outliers.

python
Copy code
def visual_2(df):
    cash_out_df = df[df['type'] == 'CASH_OUT']
    plt.figure(figsize=(8,6))
    plt.scatter(cash_out_df['oldbalanceOrg'] - cash_out_df['newbalanceOrig'], 
                cash_out_df['oldbalanceDest'] - cash_out_df['newbalanceDest'])
    plt.title('Account Balance Delta: Origin vs Destination for Cash-Out Transactions')
    plt.xlabel('Origin Account Balance Delta')
    plt.ylabel('Destination Account Balance Delta')
    plt.grid(True)
    plt.show()
    return "This scatter plot highlights cases where account balances show unusual patterns, indicating potential fraud."
4. Recommendations for Fraud Detection
Based on the analysis and visualizations, the following recommendations can be made to improve fraud detection:

Focus manual reviews on CASH-OUT and TRANSFER transactions, as these are the most common fraud-prone transaction types.
Improve the algorithm’s sensitivity to false positives by focusing on transaction amounts and timing, which were identified as key factors in fraud occurrences.
How to Run the Code

Clone the repository and navigate to the project directory.
bash
Copy code
git clone https://github.com/yourusername/transaction-fraud-analysis.git
cd transaction-fraud-analysis
Ensure that you have Python installed and the following libraries:
pandas
matplotlib
You can install the required dependencies using:

bash
Copy code
pip install pandas matplotlib
Run the Jupyter Notebook file to execute the analysis and visualize the data.
To test specific parts of the code, modify the Jupyter Notebook or create Python scripts to run the functions defined in the exercises.py file.
Conclusion

This project provided valuable insights into the patterns of fraud within mobile money transactions. By analyzing transaction data and visualizing key metrics, we were able to recommend actionable steps to improve fraud detection, reduce false positives, and enhance security measures for financial services providers.

Author: [Your Name]
Date: September 2024
License: MIT License
