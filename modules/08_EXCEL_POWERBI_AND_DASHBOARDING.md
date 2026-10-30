# Module 8 — Excel, Power Query, Power BI and dashboard interviews

## Learning outcomes
Prepare data, calculate metrics, model a star schema, write basic DAX and build dashboards that support decisions.

## 1. Excel
Know relative/absolute references, tables, sort/filter, text/date functions, `IF`, `IFERROR`, `SUMIFS`, `COUNTIFS`, `XLOOKUP`, PivotTables, charts, slicers and conditional formatting.

### Exercise
Given `Sales(Date, Region, Product, Units, NetSales)`, calculate revenue by region and product, identify the top 5 products, and show monthly trend using a PivotTable. Reconcile PivotTable total to source sum.

## 2. Power Query
Import → profile → change types → clean → merge/append → load. Merge combines columns using a join; append stacks rows. Keep transformations repeatable and inspect errors.

## 3. Data model
A star schema contains a fact table at a declared grain and dimensions describing it. Example:
- FactSales: one row per order line.
- DimDate: one row per date.
- DimProduct: one row per product.
- DimStore: one row per store.
Use one-to-many relationships from dimensions to fact where appropriate.

## 4. Measures vs calculated columns
Measures calculate in filter context at query time. Calculated columns are computed during refresh and stored. Use measures for aggregations that should respond to report filters.

## 5. DAX examples
```dax
Net Sales = SUM(FactSales[NetSales])

Units Sold = SUM(FactSales[Units])

Order Count = DISTINCTCOUNT(FactSales[OrderID])

Average Order Value =
DIVIDE([Net Sales], [Order Count])
```
If FactSales is order-line grain, distinct order count is needed. AOV definition should use the agreed revenue and order population.

## 6. Dashboard design
Audience and decision first. Use clear metric definitions, units, date range, refresh timestamp, trends and useful segmentation. Avoid chart clutter, truncated axes, unlabelled denominators and colour-only meaning.

## Independent exercises
1. Explain why a date dimension is needed for time intelligence.
2. A measure doubles after adding Product dimension. Investigate relationships and duplicate keys.
3. Design a dashboard for fulfilment operations with five KPIs and a drill-down.
4. Explain Import vs DirectQuery trade-offs.
5. Describe row-level security and how to test it.
6. Explain how you would reconcile a Power BI KPI with SQL.

### Answer guidance
1. Date dimension provides continuous calendar attributes and supports time calculations.
2. Check relationship cardinality, dimension uniqueness, bridge tables and filter direction.
3. Include on-time delivery, backlog, average/p90 fulfilment time, cancellation and volume; define denominator/time window.
4. Import often gives performance and modelling flexibility; DirectQuery queries the source and depends on source capacity/latency and feature limitations.
5. Restrict rows by user/role; test with representative identities and least privilege.
6. Match grain, filters, timezone, status, currency, refresh time and NULL handling.

## External practice for this module

1. [Microsoft Learn — Power BI](https://learn.microsoft.com/en-us/training/powerplatform/power-bi) — complete beginner learning paths on getting data, modelling and building reports.
2. [Microsoft Learn — DAX](https://learn.microsoft.com/en-us/dax/) — use the reference for SUM, CALCULATE, filter context and time intelligence.
3. [SQLBI](https://www.sqlbi.com/) — study introductory articles/videos on star schema, relationships, row context and filter context.
4. [DAX Guide](https://dax.guide/) — look up functions while completing the measures in this module.
5. [ExcelJet](https://exceljet.net/) — practise SUMIFS, COUNTIFS, XLOOKUP, date/text formulas and PivotTables.

**Applied assignment:** download a dataset from [Maven Analytics Data Playground](https://www.mavenanalytics.io/data-playground) or [Kaggle](https://www.kaggle.com/datasets). Build a star schema, 5 measures, 1 time trend, 2 useful slicers and a dashboard page. Reconcile every KPI against SQL or a spreadsheet total.

**Exit requirement:** explain fact grain, dimension relationships, measure vs calculated column, filter context and how a dashboard supports a specific decision.
