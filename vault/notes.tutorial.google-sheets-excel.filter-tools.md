---
id: HGAS1CK0zAaHORLkRwQ5k
title: Filter Tools
desc: ''
updated: 1639282097714
created: 1639108579551
---
# How to filter to get a subset data in Google Sheets

ref: 
- [Learn Google Spreadsheets | Google Sheets - Filter, Filter by Text, Date, Condition, Custom Formula, Regular Expression Tutorial](https://www.youtube.com/watch?v=e7gLjNp9Qo0)
- [Learn Google Spreadsheets | Google Sheets - Filter Views & SUBTOTAL Function Tutorial](https://www.youtube.com/watch?v=49kkP04Whn8)

Beside of basic techniques, there are some interesting advanced tips that I used

## Filter by condition using Custom formula  
Logical comparison
![custom-formula](https://i.imgur.com/YY3puM5.jpg){max-width: 300px, display: block, margin: 0 auto}

Text comparison
```javascript
=AND(MID(H2,3,1)="3", LEFT(H2,1)="5")
```

Logical test
```javascript
=OR(AND(D2="NIKE",E2>200),AND(D2="ADIDAS",E2>400))
```

Regular Expression, which is case sensitive
```javascript
=REGEXMATCH(H2,"^5.3")
```

## Filter View and SUBTOTAL function
Instead of apply `Filter` to table, I can create a `Filter View` for myself or temporary use, which make the data table less confused for other users.
![filter-view](https://i.imgur.com/q2U3h7m.jpg){max-width: 300px, display: block, margin: 0 auto}

Further I can use [SUBTOTAL](https://support.google.com/docs/answer/3093649?hl=en) function to calculate the aggregation of the filtered data
![subtotal-example](https://i.imgur.com/80hrsbn.jpg){max-width: 300px, display: block, margin: 0 auto}

## FILTER function with multiple criteria
ref: [Learn Google Spreadsheets | Google Sheets - Filter Function Tutorial, Introduction to Logical Arrays](https://www.youtube.com/watch?v=JQSlbQeEz1k)

I can also use FILTER function in Google Sheets to extract data satisfying multiple criteria, through using logical arrays within FILTER function.

Duplicate [this spreadsheet file](https://docs.google.com/spreadsheets/d/1w3nrBtRaGtHfyh6blAt0X0OIAMC8n4MOwFrOdIgdyZE/) to practice