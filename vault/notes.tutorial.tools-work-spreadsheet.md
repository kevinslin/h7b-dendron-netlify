---
id: Ruw6Q1WlSQPTSGrK5fi29
title: Tools Work Spreadsheet
desc: ''
updated: 1636711742096
created: 1636706940589
---
#  Excel and their alternatives

[Microsoft 365](https://www.microsoft.com/en-us/microsoft-365)  
[Pricing plan](https://www.microsoft.com/en-us/microsoft-365/buy/compare-all-microsoft-365-products?tab=1) starts at USD 70/year

[Google Workspace](https://workspace.google.com/)  
[Pricing plan](https://workspace.google.com/intl/en/pricing.html) starts at USD 6/month

[Rows](https://rows.com/)  
[Pricing plan](https://rows.com/pricing) starts at USD 59/month, with limited free tier  
Thoughts:
- similar to [retool](https://retool.com/) which is used to build internal tools
- read [here](https://blog.rows.com/p/delivering-more-meals-with-rows) to know how a client use `Rows` in their workflow
- They are really onto something, especially in how to work get structured data out of other systems into a spreadsheet and then work with that kind of data in the "spreadsheet way" that we've all been trained in. This is a pain point of current spreadsheets and one that Rows is addressing in a really nice way (ref: [Hacker News](https://news.ycombinator.com/item?id=29189776))

[Grid](https://grid.is/)  
[Pricing plan](https://grid.is/product/pricing) starts at USD 29/month, with good free tier  
Thoughts:
- Turn spreadsheets into interactive web documents. Exambples: [mortgage calculator](https://grid.is/@grid_templates/template-mortgage-calculator-M77pS0K3SKixlk6PaS8nWg), [sales report](https://grid.is/@grid/example-report-week-x-sales-GigKWCT9T2OZmj_pnEGlfg), [financial model explanation](https://grid.is/@jordan/saas-financial-models-an-interactive-breakdown-vriV71vcSXG4NnNYukcfhQ)
- GRID does not write back into your original spreadsheet when a GRID document is interacted with or altered
- Similar to [Causal](https://www.causal.app/)

[Causal](https://www.causal.app/)  
[Pricing plan](https://www.causal.app/pricing) starts at USD 50/month, with good free tier.
Thoughts: 
- better tools to build models and scenarios, compared to Excel
- publish beautiful, interactive report

[Spreadsheet.com](https://www.spreadsheet.com/)  
[Pricing plan](https://www.spreadsheet.com/pricing) starts at USD 11/month/creator, free for editor/commenter/viewer. With limited free tier, 2000 rows per workbook, similar to Airtable  
Thoughts:
- Rows that link together across worksheets, even across different workbooks, like tables in a relational database. Learn more [here](https://support.spreadsheet.com/hc/en-us/articles/360029505012-Quick-Start-Related-Rows-and-Lookups)
- [Row hierarchies](https://support.spreadsheet.com/hc/en-us/articles/360029860151-Quick-Start-Indenting-Rows-to-Create-Hierarchies) with parent-child relationships for things like project plans, task lists and org structures
- New ways to work with worksheet data that go beyond the traditional grid of cells, such as [Kanban views](https://support.spreadsheet.com/hc/en-us/articles/360029870251-Quick-Start-Kanban-Views) for managing workflows and responsibilities, [Gantt view](https://support.spreadsheet.com/hc/en-us/articles/4401779714964-Quick-Start-Gantt-Views-and-Project-Management) as interactive timeline to manage a project’s schedule and create task dependencies
- identical spreadsheet GUI as Excel and Google Sheets
- has similar formula [functions](https://support.spreadsheet.com/hc/en-us/categories/360001544671-Function-Reference) with identical syntax to Excel and Google Sheets

[Smartsheet](https://www.smartsheet.com/)  
[Pricing plan](https://www.smartsheet.com/pricing) starts at USD 9/month/user, min 3 users. With 30-day free trial.

[Airtable](https://www.airtable.com/)  
[Pricing plan](https://airtable.com/pricing) starts at USD 12/month. With limited free tier (1200 records per base)
Thoughts: small database use case

## The 3 types of spreadsheets

ref: [grid.is](https://medium.grid.is/the-3-types-of-spreadsheets-3d021356c002)

spreadsheet in the world is used for one of three things:
- Small databases
- Models
- Business Processes

![grid.is](https://miro.medium.com/max/875/1*gWLTwAq5U5jVGBTpJPWzgQ.png){max-width: 500px, display: block, margin: 0 auto}

**Small databases**

Spreadsheet software is the first thing a regular user fires up whenever any data needs to be collected: Contact lists, inventory, logging custom things

These files will usually not have so much as a single formula in them, and the content is often text heavy compared to other spreadsheets. These files ontain 2-dimensional data or more complicated data structures
- multi-dimensional: multiple headers in a table usually add a dimension although obviously still represented in the 2-dimensional grid (a simple intro to multi-dimensional data can be found [here](https://hjalli.medium.com/data-pivots-for-kindergartners-af754db04417))
- hierarchical: some rows in a table are of a lower level and roll up to higher level rows
- relational: data on one sheet refers to details on another

**Models**

These files are usually number-heavy and their defining characteristic is that they have formulas in them. Users are calculating something.

3 sub-categories:
- Projections: Where a lot of data is generated from a relatively small set of input parameters. A common example would be a financial projection based on a set of assumptions (often 1000s of numbers generated from <20 assumptions).
- Analysis: Where a small set of data is calculated from a large set of data, often exported some other system. A typical example would be to calculate average customer spend based on age-group on data exported from a retail system. In this case the spreadsheet is competing directly against purpose-built BI systems, and — in many respects — winning.
- Calculators: This is the most diverse sub-category. Here you’ll find spreadsheets where people are performing some sort of calculations but the balance between the amount of input and output variables is better. An example here might be a mortgage calculator.

**Business Processes**

These are business processes that are run partially or entirely on spreadsheets.

A simple example might be a workplace lunch-order: Fill in the spreadsheet before 11:30 and the order will go out. 

A higher level example might be that every department in the organization has to fill in a spreadsheet template and submit it to HR or Finance before the end of the month. There some poor back-office person aggregates the data into another spreadsheet, enters the results into the payroll system and sends it on to whoever creates the slide-deck for the upcoming board meeting.

And everything between: I’ve seen a spreadsheet that serves as the UI for a large IT company’s billing process. I’ve seen spreadsheets that generate custom portfolio reports for high net-worth individuals in a bank. I’ve seen spreadsheets that are effectively sophisticated CRM-systems.

These spreadsheets are usually accompanied by formalized or not-so-formalized workflows that rely on emailing spreadsheets around, notifying people of changes in a network drive or multiple people working on a spreadsheet stored in the cloud at the same time.

Somewhat tongue-in-cheek, I’ve theorized that every new process within an organization starts out as a spreadsheet before it is (sometimes) formalized in a purpose-built system. That formalization often comes at a great cost, and surprisingly often leads to a solution that is not only much more reliant on IT for operating and maintaining, but also a lot less flexible than the original spreadsheet creation.
