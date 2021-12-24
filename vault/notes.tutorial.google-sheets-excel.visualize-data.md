---
id: 4hL9V93O6LLwFbuHQvC8H
title: Visualize Data
desc: ''
updated: 1640317482262
created: 1640230718139
---
# Tips to visualize data in Excel

ref: [ExcelIsFun](https://www.youtube.com/watch?v=UVZcamKLJgU)

There are many inspiring example of data visualization from [zebra bi](https://zebrabi.com/)

Why visualize instead of presenting in table?  
One of the best reason: help us see patterns and trends
![table-vs-chart](https://i.imgur.com/aNNypjK.jpg){max-width: 300px, display: block, margin: 0 auto}

## Table design principles:
- Horizontal lines are generally necessary only for separating column titles from data values or when
indicating that a calculation has taken place.
![horizontal-line](https://i.imgur.com/1n3A01N.jpg){max-width: 300px, display: block, margin: 0 auto}
- In large tables, light shading can be used to differentiate columns
![alternate-color](https://i.imgur.com/gW8elAU.jpg){max-width: 300px, display: block, margin: 0 auto}

## Edit range of series in chart 
Use `Select Data Source` to edit the ranges that the chart is pointing to
![select-data](https://i.imgur.com/pYPRyWm.jpg){max-width: 300px, display: block, margin: 0 auto}

## Line chart with emphasize
Create helper column in data source to create line chart that shows revenue and emphasizes promotions for company
![line-emphasize](https://i.imgur.com/WheknBf.jpg){max-width: 300px, display: block, margin: 0 auto}

## Combo chart with a line of average - Google Sheets

ref: [Learn Google Spreadsheets](https://youtu.be/6vbferZJNJY?t=917)

![example-combo-chart](https://i.imgur.com/qS4fI21.jpg){max-width: 300px, display: block, margin: 0 auto}

Prepare the pivot table from `sales` data table. 
- Insert a new calculated field, 
    - named `Average` 
    - with the `Summarize by` option set as `Custom`
    - with `Formula`: `SUM/COUNT`
![custom-pivot-table](https://i.imgur.com/lv4ajPt.jpg){max-width: 300px, display: block, margin: 0 auto}

Then insert a `combo chart` with the recently created pivot table as `data range`