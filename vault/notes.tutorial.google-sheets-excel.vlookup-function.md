---
id: KfU16jPDGG7F3nzdlT7hl
title: Vlookup Function
desc: ''
updated: 1639888046983
created: 1639110616408
---
# VLOOKUP and its alternative

ref:
- [Learn Google Spreadsheets | VLOOKUP - Part 1](https://www.youtube.com/watch?v=0rWeMHdWvOc)
- [Learn Google Spreadsheets | INDEX MATCH - Part 5](https://www.youtube.com/watch?v=-nqLkqXnAvg)
- [Learn Google Spreadsheets | VLOOKUP - Is Sorted, Approximate Match - Part 3](https://www.youtube.com/watch?v=AwOM3yzN3so)
- [Merge Spreadsheets](https://www.mergespreadsheets.com/guides/mergespreadsheets-vlookup-indexmatch.html)
- [Access Analytic | Youtube](https://www.youtube.com/watch?v=qR3HVrhsoh4)

With `INDEX` `MATCH` combination, the lookup column don't need to be at leftmost position.
![](https://project-static-assets.s3.amazonaws.com/MergeSpreadsheets/IndexMatch1.png){max-width: 300px, display: block, margin: 0 auto}

I can use `VLOOKUP` with sorted column and `approximate match` to get the nearest match with given data.  
In the example, I need to find commission rate based on sales figures, which are defined in lookup table
![sorted-approx-match](https://i.imgur.com/D1JO6MI.jpg){max-width: 300px, display: block, margin: 0 auto}

[[DGET function|notes.tutorial.google-sheets-excel.dget-function]] is also a good alternative of `VLOOKUP`, both in Googles Sheets and Excel.

With [[QUERY function|notes.tutorial.google-sheets-excel.query-function]], I can achieve similar results in Google Sheets for `VLOOKUP`-related tasks.

Interestingly, there's a [clip](https://www.youtube.com/watch?v=qR3HVrhsoh4) that try to benchmark XLOOKUP vs INDEX MATCH with a data set of 500k rows, or 2M cells with formulas. Results tested on a `4GB RAM Virtual Machine` are as follows.

|                               | runtime | filesize  |
|-------------------------------|---------|-----------|
| original file without formula | N/A     | 5,195 KB  |
| INDEX MATCH version           | 19.12 s | 22,726 KB |
| XLOOKUP version               | 17.71 s | 22,163 KB |

Lastly, for large data set (more than 10k rows), do not use `VLOOKUP`, `INDEX MATCH` or even `QUERY`, please consider 
- [[POWER QUERY merges|notes.tutorial.google-sheets-excel.power-query.merge-query]]
- [[POWER PIVOT relationships|notes.tutorial.google-sheets-excel.relationship-in-data-model]]
- [Franchise | an open-source notebook for sql
](https://franchise.cloud/)
