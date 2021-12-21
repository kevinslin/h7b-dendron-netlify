---
id: jali2NNZqlWvDeo9bwj0W
title: Combo Chart with Avg Line
desc: ''
updated: 1638926653334
created: 1638925244720
---
# Create a combo chart with a line representing average number in Google Sheets

ref: [Learn Google Spreadsheets](https://youtu.be/6vbferZJNJY?t=917)

![example-combo-chart](https://i.imgur.com/qS4fI21.jpg){max-width: 300px, display: block, margin: 0 auto}

Prepare the pivot table from `sales` data table. 
- Insert a new calculated field, 
    - named `Average` 
    - with the `Summarize by` option set as `Custom`
    - with `Formula`: `SUM/COUNT`
![custom-pivot-table](https://i.imgur.com/lv4ajPt.jpg){max-width: 300px, display: block, margin: 0 auto}

Then insert a `combo chart` with the recently created pivot table as `data range`
