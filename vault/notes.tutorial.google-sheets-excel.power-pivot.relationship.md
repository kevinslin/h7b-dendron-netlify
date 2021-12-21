---
id: 3AVFn8txpRewVX5DvaML2
title: Relationship
desc: ''
updated: 1639892448966
created: 1639887641096
---
# What is a Relationship in Power Pivot

ref:
- [SumProduct](https://www.sumproduct.com/blog/article/power-pivot-principles/ppp-creating-relationships)
- [Microsoft | Create relationships in Diagram View in Power Pivot](https://support.microsoft.com/en-us/office/create-relationships-in-diagram-view-in-power-pivot-12e00cb6-cb4d-469c-97ce-caa08349ad76)
- [Goodly](https://www.goodly.co.in/create-relationships-power-pivot-power-bi/)
- [radacad](https://radacad.com/basics-of-modeling-in-power-bi-what-is-a-dimension-table-and-why-say-no-to-a-single-big-table)
- [Microsoft | star schema](https://docs.microsoft.com/en-us/power-bi/guidance/star-schema)
- [keboola](https://www.keboola.com/blog/star-schema-vs-snowflake-schema)

A relationship is a connection between two tables of data, based on one or more columns in each table
![relationship-table](https://support.content.office.net/en-us/media/dc2ab80d-a5aa-44d6-9f28-36c6493e2856.png){max-width: 300px, display: block, margin: 0 auto}

Supported relationships in Power Pivot and Power BI
![](https://www.goodly.co.in/wp-content/uploads/2018/10/Create-Relationships-in-Power-Pivot-and-Power-BI-5.png){max-width: 300px, display: block, margin: 0 auto}

The one to many relationship is the foundation of Power Pivot
- Dimension tables (I call them Lookup tables): 
    - on the one side of the relationship. 
    - This table keeps descriptive information that can slice and dice the data of the fact table
    - contain a relatively small number of rows
    - support `filtering` and `grouping`
- Fact tables (I call them Data tables): 
    - on the many side of the relationship. 
    - This table keeps numeric data that might be aggregated in the reporting visualizations
    - contain a very large number of rows and continue to grow over time
    - support `summarization`

## Star schema
Star schema requires modelers to classify their model tables as either `dimension` or `fact`
![star-schema-1](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/star-schema-example1.png){max-width: 300px, display: block, margin: 0 auto}
![star-schema-2](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/star-schema-example2.png){max-width: 300px, display: block, margin: 0 auto}
- Star schema stores redundant data in dimension tables, or their dimensions are denormalized.
- A simple star schema leads to simple query writing
- Faster query execution time
- Star schemas might run queries faster, but they require more storage space than snowflake schemas because of their data redundancy
- Data integrity is more at risk in star schemas than snowflake schemas. Because data is stored redundantly, multiple copies of the same data exist in the star schema’s dimensional tables. This means new inserts, updates, or deletes can compromise the integrity of data

## Snowflake schema
A snowflake schema is very similar to the simple star schema above. The main difference is that snowflake schemas split dimensional tables into further dimensional tables
![snowflake-schema](https://assets.website-files.com/5e6f9b297ef3941db2593ba1/614df5d249f1d56f764083ef_Screenshot%202021-09-24%20at%2017.47.02.png){max-width: 300px, display: block, margin: 0 auto}
- Each dimension is split until it is normalized - aka, there is no redundancy in the dimensional table, no repetition of values
- snowflake schemas require a more complex query design
- Slower query execution time
- less diskspace
- the snowflake schema is less prone to data integrity issues, because it fully normalizes dimensional tables, storing dimension data only once in the appropriate table