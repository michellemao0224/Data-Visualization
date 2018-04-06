# Data-Visualization

## Data Source
- Convert Borrower State data type to Geographic role -> State/Province
- Loan Origination Date change to string type, then custom split by ‘ ’. Convert the split result to date type.


## Data Analysis
- Customer Quality
- Loan Provider Profitability
- Credit Risk

#### Customer Quality

- Scatter Plot: IncomeRange vs. EmploymentStatus
- Bar Plot: Prosper Rating (Color: AVG[Debt to Income Ratio])
- Map: Borrower State (Color: Prosper Rating, Shape: Income Range, Filter: Years/ Quarters/ Months)

#### Loan Provider Profitability

- Comparison (Line Chart): AVR[Borrower APR], AVG[Borrower Rate], AVG[Lender Yield]
- Pie Chart: Total: LP CustomerPayment, Distribution: SUM[LP CustomerPrincipalPayment], SUM[LP InterestandFees]
- SUM[Loan Amount] across Years/ Quarters/ Months 

#### Credit Risk

- Pie Chart: Total: Estimated Effective, Distribution: SUM[Estimated Loss], SUM[Estimated Return]
- Amount Delinquent (calculate filter: >0) as ‘Delinquencies’ group.  Find this group: Employment Status, Borrower State, Prosper Rating, Income Range.
- Revolving Credit Balance (calculate filter: [Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7 ) as ‘High Liabilities’ group. Find this group: Current Delinquencies, BankcardUtilization, Debt to Income Ratio, Prosper Rating.
