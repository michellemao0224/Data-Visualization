# Data-Visualization

## Data Source
- Convert Borrower State data type to Geographic role -> State/Province
- Loan Origination Date change to string type, then custom split by ‘ ’. Convert the split result to date type.


## Data Analysis
1. Customer Quality
2. Loan Provider Profitability
3. Credit Risk

#### Customer Quality

- Bar Plot: IncomeRange (Color: EmploymentStatus, Filter: ProsperRating, Year, Loan Original Quarter)
- Bar Plot: Prosper Rating (Color: AVG[Debt to Income Ratio], Filter: Year, Loan Original Quarter)
- Map: Borrower State (Color: Number of Records, Shape: Prosper Rating, Filter: Year, Loan Original Quarter)
- Map: Borrower State (Color: Loan Original Amount, Filter: Year, Loan Original Quarter)

#### Loan Provider Profitability

- Comparison (Line Chart): AVR[Borrower APR], AVG[Borrower Rate], AVG[Lender Yield]
- Pie Chart: Total: LP CustomerPayment, Distribution: SUM[LP CustomerPrincipalPayment], SUM[LP InterestandFees]
- SUM[Loan Amount] across Years/ Quarters/ Months 

#### Credit Risk

- Pie Chart: Total: Estimated Effective, Distribution: SUM[Estimated Loss], SUM[Estimated Return]
- Amount Delinquent (calculate filter: >0) as ‘Delinquencies’ group.  Find this group: Employment Status, Borrower State, Prosper Rating, Income Range.
- Revolving Credit Balance (calculate filter: [Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7 ) as ‘High Liabilities’ group. Find this group: Current Delinquencies, BankcardUtilization, Debt to Income Ratio, Prosper Rating.
