---
id: fD1VlgtfwGzb36Dv3VajC
title: Look up Multi Criteria
desc: ''
updated: 1638929133477
created: 1638926606960
---
# Lookup with multiple criteria in Google Sheets

ref: 
- [Learn Google Spreadsheets | IF Functions from Hell in Excel & Google Sheets Formulas](https://www.youtube.com/watch?v=6cwZoKdZh94) 
- [Learn Google Spreadsheets | Lookup with Multiple Criteria - VLOOKUP, MATCH solved with DGET - Google Sheets](https://www.youtube.com/watch?v=lipWG59UJts)

Learn how to replace multiple nested IF functions (horrible like what you could encounter in this image) in Excel & Google Sheets formulas with other more manageable alternatives

![if-function-hell](https://i.imgur.com/PPP75Vv.jpg){max-width: 300px, display: block, margin: 0 auto}

Better solution: Use `VLOOKUP` with a helper table

Example use case:
- define comission rate based on 1 condition: sales revenues
- define comission rate based on combination of 2 conditions: sales name, region (`VLOOKUP` tutorial starts from [here](https://youtu.be/6cwZoKdZh94?t=691))
- assign sales representative to office location

Another solution: `DGET` with a helper table. This could be a better solution for lookup with multiple criteria, vs `VLOOKUP` or `INDEX MATCH combo`. Watch [tutorial](https://www.youtube.com/watch?v=lipWG59UJts) for more details.