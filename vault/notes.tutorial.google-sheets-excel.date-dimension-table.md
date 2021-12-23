---
id: 6rqb1ZRRrep7N7taDmmKc
title: Date Dimension Table
desc: ''
updated: 1640238861713
created: 1640233847463
---
# Create Date table as a dimension in data model

ref: [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=1243), [ExcelIsFun | pdf notes](https://people.highline.edu/mgirvin/AllClasses/348/MSPTDA/Content/PowerBIDesktop/016and017-MSPTDA-IntoductionPowerBIDesktop.pdf)

Create a helper table of `Date` dimension using [CALENDAR](https://docs.microsoft.com/en-us/dax/calendar-function-dax) DAX function

A `Date Dimension Table` help us to evaluate Time Intelligence Analysis, which should contain
- every possible day for every given year in the Date
Column in the Fact Table
- Month, MonthNumber, Year, Quarter
- Fiscal Quarter / Year / Period

![date-table](https://i.imgur.com/abhNJXE.jpg){max-width: 300px, display: block, margin: 0 auto}