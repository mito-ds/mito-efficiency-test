# Mito Efficiency Test for Finance

This repository contains data and instructions for Finance professionals to test how Mito changes their ability to write Python code. 

## Background 

Python is the most popular and rapidly growing language for Finance professionals. However, transitioning from workflows in tools like Excel to Python can take years of training and work before Finance professionals become truly productive.

This repository contains a sample Finance workflow, that includes:
- Reading in XLSX and CSV files
- Handling datatype conversions
- Generating graphs
- Creating pivot tables on time series data
- Exporting data to Excel

## Running a Mito Efficiency Test

To run a Mito Efficiency Test:
1. Download the `data` folder from this Github repository
2. See the **Workflow Description** in this README
3. Complete the workflow with Python in a Jupyter notebook.
4. Complete the workflow with Python AND Mito in a Jupyter notebook -- using Mito for the analysis.

You can either use Python + Mito first, or use Python first. If you are running this test with multiple users, switch off. 

### What to track while completing the workflow
1. How long does it take to complete the workflow working with just Python?
2. How long does it take to complete the workflow when you use Mito AND Python?
3. How often and where do you get stuck in either case?
TODO: add more? 

## Timeline 

## Workflow Description

You're an analyst, doing performance analysis on your portfolio. You have a dataset called `data/Company List.xlsx`, which is an internal Excel document that tracks your full portfolio. Furthermore, you have a bunch of data in `data/stocks` that contains stock information for all the tickers in your portfolio.

You're aiming to create two major artifacts:
1. A bar chart showing the percentage of your portfolio of the companies that have the highest five highest percentages (TODO: rephrase)
2. An exported Excel document that has the results of a pivot table, showing the average trading volume for each of these five stocks for every month

### The Workflow Steps

#### A: Import portfolio data
1. Import the `Company_List` tab from `data/Company List.xlsx`
2. Remove the `Total` row from the bottom of the `Company_List` dataframe

#### B: Calculate portfolio percentage 
1. Create a new column in your dataframe for `Portfolio Percentage` (TODO: what should this be called)
2. Make each cell in this column equal to the percentage of this 

#### C: Filter down the companies 
1. Filter down to only the five companies that have the highest portfolio percentages

#### D: Create a bar chart of portfolio percentage
1. Create a new bar chart
2. On the X axis, include these 5 company names. On the Y axis, show the current `Portfolio Percentage` of each company. 
3. **This graph is one final artifact, so save it as a PNG**

#### E: Import relevant stock prices
1. Import `data/stocks/{ticker}.csv` for each of these five companies
2. Concatenate these five datasets together, preserving all entries and all columns
3. Ensure that the `Date` column is a datetime dtype

#### F: Create a pivot table of stock volume
1. Create a new pivot table, that splits the data based on:
    - Rows: the year and month
    - Columns: the top 5 stocks
    - Values: the average volume over that month

#### G: Export your pivot table to Excel 
1. Export this pivot table to Excel, for future presentation

# Hints

This section contains hints that users can refer to incase they get stuck on any specific step. We provide these hints so that users. One useful met

### Python Hints

#### A: Import portfolio data
1. Use [`pd.read_excel`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_excel.html) to read in dataframe
2. Use [`df.drop`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.drop.html) to delete rows

#### B: Calculate portfolio percentage 
1. Use [`df.insert`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.insert.html)

#### C: Filter down the companies 
1. Filter down to only the five companies that have the highest portfolio percentages

#### D: Create a bar chart of portfolio percentage
1. Create a bar chart with [Plotly's Bar Chart](https://plotly.com/python/bar-charts/)

#### E: Import relevant stock prices
1. Import CSV files with [`pd.read_csv`](https://pandas.pydata.org/pandas-docs/stable/reference/api/pandas.read_csv.html)
2. Concatenate dataframes with [`pd.concat`](https://pandas.pydata.org/docs/reference/api/pandas.concat.html)
3. Change column types with [`astype`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.astype.html)

#### F: Create a pivot table of stock volume
1. Create a pivot table in Pandas with [`df.groupby`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.groupby.html) or [`df.pivot_table`](https://pandas.pydata.org/docs/reference/api/pandas.pivot_table.html)

#### G: Export your pivot table to Excel 
1. Download dataframes with [`df.to_excel`](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.to_excel.html)

### Python + Mito Hints

In general, if you need a hint on how to use Mito: use Mito like you use Excel.

#### A: Import portfolio data
1. Use Mito's `Import` button for XLSX importing
2. Delete rows like Excel

#### B: Calculate portfolio percentage 
1. Insert columns and write formulas like Excel

#### C: Filter down the companies 
1. Filter down to only the five companies that have the highest portfolio percentages

#### D: Create a bar chart of portfolio percentage
1. Use the Graph button to create a bar graph

#### E: Import relevant stock prices
1. Use Mito's `Import` button for XLSX importing
2. Concat with the `Merge` > `Concat` button
3. Change dtypes with the `dtype` button in the toolbar

#### F: Create a pivot table of stock volume
1. Create a pivot table with the `Pivot` button in the toolbar

#### G: Export your pivot table to Excel 
1. Export this pivot table to Excel, for future presentation



