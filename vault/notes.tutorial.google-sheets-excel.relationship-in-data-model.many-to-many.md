---
id: 9jnYx0U5MOjmlofcAFknZ
title: Many to Many
desc: ''
updated: 1640138229719
created: 1640134068731
---
# Many-to-many relationship

ref: [Microsoft](https://docs.microsoft.com/en-us/power-bi/transform-model/desktop-many-to-many-relationships)

Before the July 2018 release of Power BI Desktop, we use a workaround which is creating a `factless fact table` as a `bridging table`
![bridging-table](https://docs.microsoft.com/en-us/power-bi/guidance/media/star-schema/factless-fact.png){max-width: 300px, display: block, margin: 0 auto}

After the July 2018 release of Power BI Desktop, we can use directly `relationships with a many-many cardinality`
![many-many-relationship](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-many-to-many-relationships/many-to-many-relationships_01.png){max-width: 300px, display: block, margin: 0 auto}

Benefits of using directly the `many-many cardinality` newer approach are as follows:
-  The values shown don't include a blank row that accounts for mismatched rows in the other table. 
- Also, the values don't account for rows where the column used in the relationship in the other table is null

| Workaround | Many-many cardinality |
|---|---|
| ![workaround-1](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-many-to-many-relationships/many-to-many-relationships_10.png){max-width: 300px, display: block, margin: 0 auto}<br>![workaround-2](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-many-to-many-relationships/many-to-many-relationships_11.png){max-width: 300px, display: block, margin: 0 auto} | ![direct-cardinality](https://docs.microsoft.com/en-us/power-bi/transform-model/media/desktop-many-to-many-relationships/many-to-many-relationships_12.png){max-width: 300px, display: block, margin: 0 auto} |