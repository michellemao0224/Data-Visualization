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

- Comparison (Line Chart & Dual Axis): AVR[Borrower APR], AVG[Borrower Rate], AVG[Lender Yield]
- Pie Chart: SUM[LP InterestandFees], Distribution: ProsperRating
- Columns: SUM[Loan Amount] , Rows: AVG[Estimated Return] (Percent of Total), Color: ProsperRating, Shape: AVG[BorrowerAPR]

#### Credit Risk

- Dual Combination: Columns: Year(Loan Date), Rows: AVG[Debt To Income Rate], AVG[Current Delinquencies], Color: ProsperRating
- Amount Delinquent (calculated field: [Amount Delinquent] > 0 AND NOT ISNULL([Amount Delinquent])) as ‘Delinquencies’ group.  Find this group: Bar Plot: Columns: Delinquencies, Prosper Rating, Rows: SUM[Number of Records](Percent of Total), Details: AVG[Details: Debt To Income Ratio], AVG[PublicRecordsLast10Years]
- Revolving Credit Balance (calculated field: ([Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7) AND NOT ISNULL([Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7) ) as ‘Liabilities’ group. Find this group: Bar Plot: Columns: Liabilities, Prosper Rating, Rows: SUM[Number of Records](Percent of Total), Details: AVG[Details: Debt To Income Ratio], AVG[Bankcard Utilization]

