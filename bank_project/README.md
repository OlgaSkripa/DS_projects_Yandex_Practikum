# Bank Borrower Reliability Under Incomplete Information

**Format:** Jupyter Notebook

## Project description
**Client:** the bank’s Credit Department.  
**Input data:** statistics on clients’ creditworthiness provided by the bank.  
**Object of study:** the bank borrower.  
**Subject of study:** borrower reliability.

The results of this analysis can be used to support the development of a **credit scoring** model — a system that assesses a potential borrower’s ability to repay a loan.

## Tasks
- Develop a data preprocessing approach;
- Handle missing values and invalid entries (artefacts);
- Review duplicate records;
- Answer the following questions:
  - Is there a relationship between having children and repaying the loan on time?
  - Is there a relationship between marital status and repaying the loan on time?
  - Is there a relationship between income level and repaying the loan on time?
  - How do different loan purposes affect on-time repayment?

## Libraries and tools
- Python
- Jupyter Notebook
- pandas
- numpy
- re

## Conclusion
Within the scope of this work, the following tasks were completed:

- Data preprocessing was carried out:
  - anomalous values and missing data were identified;
  - an approach to handling them was developed, documented, and applied;
  - variables required for the analysis were categorised;
- The research questions were answered using summary tables.

_**Practical significance:**_  
The preprocessing performed in this work enables the cleaned dataset to be used for further analysis and for building credit scoring models. The resulting summary tables help assess how borrower reliability varies with selected client characteristics.

_**Recommendations for data collection:**_
- Review the logic used to compute `days_employed` for pensioners and unemployed clients;
- Provide clear, standardised guidance for recording values in the `purpose` column.
