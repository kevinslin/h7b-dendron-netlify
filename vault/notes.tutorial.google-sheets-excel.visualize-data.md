---
id: 4hL9V93O6LLwFbuHQvC8H
title: Visualize Data
desc: ''
updated: 1641601458717
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
ref: [ExcelIsFun](https://youtu.be/UVZcamKLJgU?t=2062)

Create a helper column in data source to create line chart that shows revenue and emphasizes promotions for company
![line-emphasize-1](https://i.imgur.com/WheknBf.jpg){max-width: 300px, display: block, margin: 0 auto}
![line-emphasize-2](https://i.imgur.com/IbNKVmn.jpg){max-width: 300px, display: block, margin: 0 auto}

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
- create a `DAX measure` to define the color conditions of bar chart, based on `what-if` variable.
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

## Highlight datapoint in chart
ref: [How to Power Bi](https://www.youtube.com/watch?v=hmk6PxDtbNs)

![highlight-datapoint](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-04_221207_up2R4dkrg.jpg?updatedAt=1641331341158){max-width: 300px, display: block, margin: 0 auto}

Idea: create a new `measure` to catch the criteria (in this example is the average of sales), then apply conditional format with color.

![measure-average](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-04_223212_w1A67u7EQ.jpg?updatedAt=1641331947847){max-width: 300px, display: block, margin: 0 auto}

## Small Multiples in Power BI
ref: [Microsoft](https://docs.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-small-multiples), [How to Power BI](https://www.youtube.com/watch?v=fYogZa7xOa8)

`Small Multiples`, or `trellising`, splits a visual into multiple versions of itself. The versions are presented side by side, with data divided across these versions by a chosen dimension. For example, a small multiple could split a `sales by product` column chart across countries or customer segments
![small-multiples-1](https://docs.microsoft.com/en-us/power-bi/visuals/media/power-bi-visualization-small-multiples/small-mulitple-sales-category-region.png){max-width: 300px, display: block, margin: 0 auto}
![small-multiples-2](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_224205_hhUV6OCqY8w.jpg?updatedAt=1641418975589){max-width: 300px, display: block, margin: 0 auto}

## Highlight a Date Range
ref: [How to Power BI](https://www.youtube.com/watch?v=gxYguoBQF4U)

![highlight-date-range](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_231346_2hYR54Jbn.jpg?updatedAt=1641420840649){max-width: 300px, display: block, margin: 0 auto}
Idea:
- connect `X-axis constant lines` to a date range slicer
- then use `Shade region` to blur the area outside of selected date range
- create a `DAX measure` to show the summary aggregation of selected period

## Custom period Slicer
ref: [How to Power BI](https://www.youtube.com/watch?v=Aom_81rvCVw)

Create a `Slicer` with custom date period 
![custom-slicer](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_234316_oyx2ntfqO.jpg?updatedAt=1641422609706){max-width: 300px, display: block, margin: 0 auto}

Idea:
- using [SELECTCOLUMN](https://docs.microsoft.com/en-us/dax/selectcolumns-function-dax) function, create a helper table with all the dates within the custom date period, then put it in a filter
![](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-05_235006_aGmeTB2nH.jpg?updatedAt=1641423016614){max-width: 300px, display: block, margin: 0 auto}
- then connect this helper table to the `dimDate` dimension table

## Combine Actual and Forecast in one line chart
ref: [How to Power BI](https://www.youtube.com/watch?v=_TAGpAJ9rTQ)

![actual-forecast](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_000746_u-GLoNZvZ.jpg?updatedAt=1641424081902){max-width: 300px, display: block, margin: 0 auto}

Idea:
- create a `DAX measure` called `actual & forecast` to combine data points from both `actual` sales number and `forecast`
![example-combined-sales](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_001451_iv7yPBXttGI.jpg?updatedAt=1641424501508){max-width: 300px, display: block, margin: 0 auto}
![dax-measure-combined-sales](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_001832_ZG-e280Uu.jpg?updatedAt=1641424730321){max-width: 300px, display: block, margin: 0 auto}
- then draw a line chart with 2 series `actual` and `actual & forecast`, and apply color formatting for each serie.

## Dynamic benchmark range
ref: [How to Power BI](https://www.youtube.com/watch?v=PlMvvKEPgfA)

Situation: I need a shaded area which illustrate the varying range of forecast value (upper limit forecast vs lower limit forecast), then a line to show how the actual value is, vs the forecast.

![dynamic-benchmark-range](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_125059_i-W4tI8Zl.jpg?updatedAt=1641469912975){max-width: 300px, display: block, margin: 0 auto}

Idea:
- create 2 `DAX measure` to catch the `forecast - upper limit` and `forecast - lower limit`, with a `what-if parameter` to simulate the variance of the 2 forecast upper and lower limit.
- apply color formatting as `white` for the `forecast -lower limit` serie, in order to visualize a range of forecast value
![color-formatting](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_125952_W0CNpRRRag.jpg?updatedAt=1641470403873){max-width: 300px, display: block, margin: 0 auto}

## Show multiple forecast in one chart
ref: [How to Power BI](https://www.youtube.com/watch?v=dWyieDU4zWY)

Situation: I need to show forecast of sales data from multiple department, and how accurate the forecast vs actual data.

![multiple-forecast](https://ik.imagekit.io/casa/h7b-dendron/Screenshot_2022-01-06_141618_BN-7rDV-et.jpg?updatedAt=1641475002328){max-width: 300px, display: block, margin: 0 auto}

Idea: create `DAX measure` to show or hide data series depending on chosen slicer, then apply conditional formatting for color of each series. 

## Helpful resources:

![[notes.tutorial.google-sheets-excel.power-bi#add-on-for-dashboard-reporting,1]]