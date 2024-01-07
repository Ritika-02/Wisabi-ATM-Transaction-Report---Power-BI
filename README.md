# Wisabi Bank ATM Transaction Report 


## Data Processing Steps

### Stage 1: Data Loading and Renaming

1. Loaded the data folder, opening a new source in Power Query.
2. Fetched 5 txt/csv files and renamed them for clarity.

### Stage 2: Transaction Table Modifications

1. Removed the 'source.name' column.
2. Created a new custom column named 'duration' by subtracting (Transaction_end_time - Transaction_start_time).
3. Converted 'transaction_start_time' to a time-based column in hours.
4. Changed 'transaction_start_time' to a Date-only format, renaming the column as 'Date'.

### Stage 3: Customer Table Modifications

1. Added an 'Age' column based on the birth date formula.
2. Rounded up the 'Age' column.
3. Created a conditional column based on age ranges.

### Stage 4: Relationships and Model Setup

1. Deleted existing relationships among the tables.
2. Established new relations based on Location ID, Hour, Transaction ID, Cardholder ID, and Date.
3. Marked the calendar table as the date table.

### Stage 5: DAX Measures

1. Created a Measure Table with a blank() function.
2. Added various measures, including average_amount, transaction_count, transaction_amount, number_of_customers, transaction_frequency, utilization_rate, average_duration, and % Transactions.

### Stage 6: Report Visualization

#### Overview Page

- Clustered bar graph: X-axis - average_amount, Y-axis - State, Legend - TransactionTypeName.
- Area chart: X-axis - Hour_Start_Time, Y-axis - transaction_count, Legend - State.
- Line chart: X-axis - Month Name, Y-axis - transaction_amount, Secondary y-axis - transaction_count.
- Azure Map: Location - State, Size - Utilization Rate.
- Scatter chart: Values - State, X-axis - average_duration, Y-axis - average_amount, Legend - TransactionTypeName, Size - number_of_customers, Play Axis - End of Week.
- Cards for transaction_amount and transaction_count.

#### Demography Page

- Stacked column chart: X-axis - Age Group, Y-axis - transaction_count, Legend - TransactionTypeName.
- Donut chart: Legend - TransactionTypeName, Values - transaction_count.
- Stacked bar chart: X-axis - transaction_frequency, Y-axis - Age Group.
- Stacked bar chart: X-axis - average duration, Y-axis - State, Legend - TransactionTypeName.
- Decomposition Tree: Analyze - % Transactions, Explain by - TransactionTypeName, IsWisabi, Occupation.

### Canvas Settings

#### Overview Page

- Type: Custom
- Height: 960
- Width: 1550

#### Demography Page

- Type: Custom
- Height: 950
- Width: 1450

### Home Page

- Created a new page named 'Home.'
- Added a background image.
- Utilized the Scroller visual from Power BI service with Category - Location Name and Measure Absolute - transaction_count.


## Viewing the Report

For an enhanced and interactive experience, you can view the report on my [Novypro Dashboard](https://www.novypro.com/project/wisabi-bank-atm-transactions).

## Repository Contents

The repository contains the following:

- **Data:** Raw data files used in the report.
- **Dashboard Background Images:** Images used as backgrounds in the Power BI report.
- **Images:** Other images used within the report.
- **Final Report:** The Power BI report file (`Wisabi_Bank_ATM_Report.pbix`).

## Support and Contributions

For inquiries or support, please contact (ritikabhandari049@gmail.com). Contributions are welcome; 



Enjoy analyzing your Wisabi Bank ATM transactions!

