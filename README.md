# Data-Visualization

## Data Source
- Convert Borrower State data type to Geographic role -> State/Province
- Loan Origination Date change to string type, then custom split by ‘ ’. Convert the split result to date type.


## Data Analysis
1. Customer Quality
2. Loan Provider Profitability
3. Credit Risk

#### Customer Quality

- Bar Plot: Columns: Prosper Rating Group, Rows:  SUM[Number of Records] (Color: AVG[Debt To Income Ratio], Filter: ProsperRating, Year, Loan Original Quarter) Find Prosper Rating, group exclude NULL, then set a new group named “Prosper Rating Group”
- Bar Plot: Rows: Income Range (group), Columns: SUM[Number of Records] (Color: Employment Status, Filter: Year, Loan Original Quarter) Find Income Range, group $0 and not employed as “$0”, then set a new group named “Income Range (group)”.
- Map: Borrower State (Color: Number of Records, Shape: Prosper Rating Group, Filter: Year, Loan Original Quarter, Detail: Borrower State) Find Prosper Rating, calculated field: “IF NOT ISNULL([Prosper Rating]) THEN [Prosper Rating] END” as “Prosper Rating Group”
- Map: Borrower State (Color: SUM[Loan Original Amount], Filter: Year, Loan Original Quarter, Detail: Borrower State)

#### Loan Provider Profitability

- Comparison (Line Chart & Dual Axis & Trend Line): AVR[Borrower APR], AVG[Borrower Rate], AVG[Lender Yield]
- Pie Chart: Angle: SUM[LP InterestandFees], Color: ProsperRating, Label: SUM[LP InterestandFees], ProsperRating
- Columns: SUM[Loan Amount] , Rows: SUM[Estimated Return] (Percent of Total), Color: ProsperRating, Shape: ProsperRating

#### Credit Risk

- Dual Combination: Columns: Year(Loan Date), Rows: AVG[Current Delinquencies], Color: ProsperRating
- Amount Delinquent (calculated field: [Amount Delinquent] > 0 AND NOT ISNULL([Amount Delinquent])) as ‘Delinquencies’ group.  Find this group: Pie Chart: Columns: Delinquencies, Color: Prosper Rating, label: SUM[Number of Records](Percent of Total) and Prosper Rating, angle: SUM[Number of Records]
- Revolving Credit Balance (calculated field: ([Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7) AND NOT ISNULL([Revolving Credit Balance] / [Available Bankcard Credit] >= 0.7) ) as ‘Liabilities’ group. Find this group: Pie Chart: Columns: Liabilities, Color: Prosper Rating, label: SUM[Number of Records](Percent of Total) and Prosper Rating, angle: SUM[Number of Records]

