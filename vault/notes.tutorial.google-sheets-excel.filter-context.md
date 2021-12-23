---
id: Er7oNzJ8GUxYfEn8MilnN
title: Filter Context
desc: ''
updated: 1640241040141
created: 1640236804623
---
# Filter context vs Row context in different Microsoft 365 products

ref: [sqlbi](https://www.sqlbi.com/articles/row-context-and-filter-context-in-dax/), [towards datas cience | archived pdf](https://app.box.com/s/s5toz7ei8uuqcxoirfinm0i3jmiftsly), [Microsoft](https://docs.microsoft.com/en-us/learn/modules/dax-power-bi-modify-filter/), [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=2443)

Filter context describes the filters that are applied during the evaluation of a measure or measure expression

Filters can be applied directly to columns, like a filter on the Fiscal Year column in the Date table for the value FY2020. Additionally, filters can be applied indirectly, which happens when model relationships propagate filters to other tables. For example, the Sales table receives a filter through its relationship with the Date table, filtering the Sales table rows to those with an OrderDateKey column value in FY2020.

A clip explaining the concept of filter context in Power BI by [ExcelIsFun](https://youtu.be/nBu1Bqa1jjs?t=2443). I found it's easier to understand.

The row context does not propagate automatically through relationships, whereas the filter context does traverse relationships independently from the DAX code. However, you can control the filter context and its propagation using DAX functions

Note to me: When I encounter problems with DAX related to model relationship, filter context, or need explanation on how the Context Transition works under row context and filter context, please watch again this clip from [ExcelIsFun](https://youtu.be/eIaKC6zLmb0?t=3394)