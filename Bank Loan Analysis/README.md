## Bank Loan Analysis Project

This project focuses on analyzing bank loan data using a combination of **MS SQL** for data extraction and **Power BI** for creating interactive visualizations. The goal is to explore loan application patterns, identify key factors affecting loan approvals, and provide meaningful insights that can aid decision-making processes for banks and financial institutions.

### Project Highlights:
- **Data Extraction with MS SQL:** The raw loan data was extracted, filtered, and transformed using complex SQL queries to ensure efficient and accurate data processing.
- **Power BI Visualizations:** An array of interactive and insightful dashboards were built in Power BI, enabling users to explore loan data, customer demographics, loan status distributions, and approval patterns.
- **Key Insights:** Visualizations include loan approval rates by gender, income levels, loan amounts, and credit history. These insights help in understanding customer profiles and loan risk factors.
- **Decision Support:** The project provides actionable insights for improving loan approval strategies and identifying risk patterns in loan applications.

### How to Use:
- The **SQL scripts** used for data extraction are available in the repository.
- The **Power BI file (.pbix)** can be downloaded to explore the dashboards and insights.
  
### Data Description :

| Feature     | Description                     |
| :---------- | :------------------------------ |
| `Loan ID`| unique identifier assigned to each loan application or loan account      |
| `Address State` | indicates the borrower's location    |
| `Employee Length`| borrower's employment stability      |
| `Employee Title`| borrower's occupation or job title      |
| `Grade `| risk classification assigned to the loan based on creditworthiness     |
| `Sub Grade ` | risk assessment within a grade, providing additional risk differentiation   |
| `Home Ownership `| loan's origination date    |
| `Issue Date `| a unique code to identify a bike user     |
| `Last Credit Pull Date `| records when the borrower's credit report was last accessed     |
| `Last Payment Date ` | marks the most recent loan payment received   |
| `Loan Status `| the current state of the loan      |
| `Next Payment Date `| estimates the date of the next loan payment     |
| `Purpose ` | the reason for the loan    |
| `Term `| the duration of the loan in months    |
| `Verification Status `| borrower's financial information has been verified   |
| `Annual Income `| borrower's total yearly earnings     |
| `DTI (Debt-to-Income Ratio) ` | borrower's debt burden relative to income  |
| `Installment `| fixed monthly payment amount for loan repayment      |
| `Interest Rate` | annual cost of borrowing expressed as a percentage |
| `Loan Amount` | total borrowed sum |

## Dashboard
To the Dashboard : <a href= "http://tiny.cc/i8ynzz"> Click here for Data Visulaization </a>

## Measures
1. Total Loan Applications = COUNT(financial_loan[id])
2. MTD Loan Applications = CALCULATE(TOTALMTD([Total Loan Applications], 'Date Table'[Date]))
3. PMTD Loan Applications = CALCULATE([Total Loan Applications], DATESMTD(DATEADD('Date Table'[Date],-1,MONTH)))
4. MoM Loan Applications = ([MTD Loan Applications]-[PMTD Loan Applications])/[PMTD Loan Applications]
5. Total Funded Amount = SUM(financial_loan[loan_amount])
6. MTD Funded Amount = CALCULATE(TOTALMTD([Total Funded Amount], 'Date Table'[Date]))
7. PMTD Funded Amount = CALCULATE([Total Funded Amount], DATESMTD(DATEADD('Date Table'[Date],-1,MONTH)))
8. MoM Funded Amount = ([MTD Funded Amount]-[PMTD Funded Amount])/[PMTD Funded Amount]
9. Total Amount Received = SUM(financial_loan[total_payment])
10. MTD Amount Received = CALCULATE(TOTALMTD([Total Amount Received], 'Date Table'[Date]))
11. PMTD Amount Received = CALCULATE([Total Amount Received], DATESMTD(DATEADD('Date Table'[Date],-1,MONTH)))
12. MoM Amount Received = ([MTD Amount Received]-[PMTD Amount Received])/[PMTD Amount Received]
13. Avg Interest Rate = AVERAGE(financial_loan[int_rate])
14. MTD Avg Rate = CALCULATE(TOTALMTD([Avg Interest Rate], 'Date Table'[Date]))
15. PMTD Avg Rate = CALCULATE([Avg Interest Rate], DATESMTD(DATEADD('Date Table'[Date],-1,MONTH)))
16. MoM Avg Rate = ([MTD Avg Rate]-[PMTD Avg Rate])/[PMTD Avg Rate]
17. Avg DTI = AVERAGE(financial_loan[dti])
18. MTD DTI = CALCULATE(TOTALMTD([Avg DTI], 'Date Table'[Date]))
19. PMTD DTI = CALCULATE([Avg DTI], DATESMTD(DATEADD('Date Table'[Date],-1,MONTH)))
20. MoM DTI = ([MTD DTI]-[PMTD DTI])/[PMTD DTI]
21. 
