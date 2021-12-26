---
id: 4hL9V93O6LLwFbuHQvC8H
title: Visualize Data
desc: ''
updated: 1640554065444
created: 1640230718139
---
# Tips to visualize data in Microsoft 365

ref: [ExcelIsFun](https://www.youtube.com/watch?v=UVZcamKLJgU)

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

## Combo chart with a dynamic reference line - Power BI

ref: [How to Power BI](https://www.youtube.com/watch?v=9TyKMEoUMy0)

![dynamic-ref-line](https://i.imgur.com/WSw6P3L.jpg){max-width: 300px, display: block, margin: 0 auto}

Idea: 
- create a `what-if` parameter with name `Prices` to simulate.
- create a `measure` to define the color conditions of bar chart, based on `what-if` variable.
  ```dax
  AboveAvgPrice? =
  IF(
      [Avg Price per Person] >= [Prices Value],
      1,
      0
  )
  ```
- apply conditional formatting to that `measure`

## Dynamic Quadrant Analysis - Power BI

ref: [How to Power BI](https://www.youtube.com/watch?v=W_aAWZRgA8s)

![dynamic-quadrant-1](https://i.imgur.com/WY8zchw.jpg){max-width: 300px, display: block, margin: 0 auto}
![dynamic-quadrant-2](https://i.imgur.com/19Jeutz.jpg){max-width: 300px, display: block, margin: 0 auto}
Idea: 
- Create 2 custom reference line to draw a quadrant,
- create a `what-if` parameter to simulate, 
- create a `measure` to define color conditions of data point
  ```dax
  CF Quadrants = 
  VAR TargetPrice = [Avg Price per Person] <= [MaxAvgPricePerPerson]
  VAR TargetReviews = [# Reviews] >= [MinNumberOfReviews]
  VAR Result =
  SWITCH(
      TRUE(),
      TargetPrice && TargetReviews = FALSE(), 1,
      TargetPrice && TargetReviews, 2,
      TargetPrice = FALSE() && TargetReviews = FALSE(), 3,
      TargetPrice = FALSE() && TargetReviews,4
  )
  RETURN
      Results
  ```
- Then apply conditional formatting to the newly created `Measure` 

## Helpful resources:

![[notes.tutorial.google-sheets-excel.power-bi#add-on-for-dashboard-reporting,1]]