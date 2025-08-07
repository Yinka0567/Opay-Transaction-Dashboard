# Opay-Transaction-Dashboard
This project is a professional Power BI dashboard built using real Opay transaction data. It provides clear insights into personal financial activity by analyzing income, expenses, and transaction patterns.
# Project Topic: Personal Financial Dashboard: Analyzing My Opay Spending with Power BI
## Overview
Managing finances effectively starts with understanding where your money goes. I often found myself wondering about my spending habits and how consistent my savings behavior really was. 
To gain clarity, I decided to perform a detailed analysis of my Opay transaction history using Power BI and Python.
##  Data Acquisition & Preparation

I obtained my **Opay account statement** in **PDF format**, which included two sections:

- **Balance Summary** – containing my transaction history
- **OWealth Summary** – related to investment activity

### Tools Used:
- **Python** – to convert PDF into Excel using `pdfplumber` and `pandas`
- **Microsoft Excel** – for initial data cleaning
- **Power BI Desktop** – for modeling and dashboard creation

### Data Cleaning:
- Removed the **OWealth Summary** section from the dataset
- Added a custom column called **“Status”** to classify transactions as either **Credit** or **Debit**
- Split the **“Descriptions”** column using Power BI’s **“Split by Delimiter”** to better categorize transactions (e.g., Airtime, Transfers, Funding)

  ## 📈 Power BI Analysis & DAX Modeling

I imported the cleaned dataset into **Power BI** and created several custom measures using **DAX**, including:

- `Total Credit` – Sum of all incoming transactions
```
Total Credit = CALCULATE(SUM(Sheet1[Amount]),Sheet1[Status]="Credit")
```

- `Total Debit` – Sum of all outgoing transactions

```
Total Debit = CALCULATE(SUM(Sheet1[Amount]), Sheet1[Status]="Debit")
```

- `Total Transaction` - Sum of all Transaction
```
Total Transaction = SUMX(Sheet1,ABS(Sheet1[Amount]))
```

- `Transaction Count` – Number of transactions over time
```
Transaction Count = COUNTROWS(Sheet1)
```

### Data Summary and Insight
This dashboard provides a comprehensive personal finance analysis using transaction data from my Opay account. It highlights income sources, spending patterns, saving behavior, and overall financial health over time.
Interactive visuals offer insights into credit vs debit flows, transaction categories, monthly balances, and top spending areas.

<img width="879" height="502" alt="image" src="https://github.com/user-attachments/assets/98b9b251-a85e-46b7-868b-56cf0141eb67" />

#### Key Dashboard Features
The dashboard gives a complete overview of my personal finances:
- KPI Cards: Quick glance at total credit, debit, balance, and number of transactions.
- Income Distribution by Category: Pie chart showing where money comes in (e.g., Add Money, Interest)
- Income vs Expense by Month: Stacked bar chart showing monthly cash inflows and outflows.
- Balance Over Time: Line chart tracking account balance month-by-month.
- Top Transactions: Bar chart highlighting high-value transaction categories.
- Transaction Details Table: Drill-down into individual transactions and their amounts.
- Slicer: On Month, Credit and Debit

#### Key Takeaways
- Auto-savings and Transfers make up a large portion of debits
- Transfer and Manual Add Money are the main credit source, showing lack of automated income streams
- Account balance is trending downward, indicating the need for better budget control
- Although my account recorded a high balance in July, it was also accompanied by a significant volume of debit transactions during the same period.

## Usage

You can open the `.pbix` file using **Power BI Desktop**.

To replicate this with your own data:
1. Export your Opay statement as a PDF
2. Convert to Excel using Python or a converter
3. Clean data by focusing on Balance Summary
4. Load into Power BI and recreate visuals using your values

## Author
**Enoch Amoo**
_Data Scientist_
[GitHub Profile](https://github.com/Yinka0567)
[linkedIn Profile](https://www.linkedin.com/in/amoo-enoch-b4515b24a/)
