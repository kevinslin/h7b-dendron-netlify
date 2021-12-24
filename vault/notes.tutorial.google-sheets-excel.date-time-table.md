---
id: 6rqb1ZRRrep7N7taDmmKc
title: Date Time Table
desc: ''
updated: 1640320534639
created: 1640233847463
---
# Create Date Time table as a dimension in data model

ref: [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=1243), [ExcelIsFun | pdf notes](https://people.highline.edu/mgirvin/AllClasses/348/MSPTDA/Content/PowerBIDesktop/016and017-MSPTDA-IntoductionPowerBIDesktop.pdf), [Microsoft | Create date tables in Power BI Desktop](https://docs.microsoft.com/en-us/power-bi/guidance/model-date-tables), 

In Power BI Desktop, there is a feature called [Auto date/time](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-auto-date-time) to support convenient time intelligence reporting based on date columns loaded into a model
![auto-date-time](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-auto-date-time/auto-date-time-hidden-table-example-rows.png){max-width: 300px, display: block, margin: 0 auto}

However, `Auto date/time` tables are permanently hidden, even from modelers. They cannot be seen in the Fields pane or the Model view diagram, and its rows cannot be seen in Data view. Also, the table and its column cannot be directly referenced by DAX expressions

Hence, if we need more date/time measures, we can disable the `Auto date/time` for our specific file, and create manually a new helper table of `Date` dimension using [CALENDAR](https://docs.microsoft.com/en-us/dax/calendar-function-dax) DAX function

A `Date Dimension Table` help us to evaluate Time Intelligence Analysis, which should contain
- every possible day for every given year in the Date
Column in the Fact Table
- Month, MonthNumber, Year, Quarter
- Fiscal Quarter / Year / Period

![date-table](https://i.imgur.com/abhNJXE.jpg){max-width: 300px, display: block, margin: 0 auto}
