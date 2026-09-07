# DAX & Data Visualization — Power BI Report

A Power BI (`.pbix`) sample report built to practice **DAX measures** and **core Power BI visual types** on a retail/orders dataset (Superstore-style: orders, order details, and sales targets).

## 📁 File

- `DAX___Data_visualization.pbix`

## 🗂️ Data Model

The report's semantic model contains four tables, related on a star-schema layout:

| Table | Role |
|---|---|
| **Date Table** | Date dimension (drives the time hierarchy used in Line Chart / Matrix visuals) |
| **List of Orders** | Order-level dimension data (e.g. State, City) |
| **Order Details** | Fact table — line-item sales, quantity, profit, category/sub-category |
| **Sales target** | Target/goal table — category-level sales targets |

## 📊 Report Pages

The report contains **9 pages**, each built around a specific visual type:

| Page | Visual Type | Fields Used |
|---|---|---|
| Clustered Column Chart | `clusteredColumnChart` | Category (Sales target) • Total Sales & Total Target (Y-axis) |
| Donut Chart | `donutChart` | Sub-Category (Order Details) • Max Profit Margin |
| Line Chart | `lineChart` | Date hierarchy (Date Table) • Total Sales |
| Scatter Chart | `scatterChart` | Sub-Category • Quantity (X) vs. Profit (Y) |
| Card | `cardVisual` + `tableEx` | Total Sales, Total Target cards • table by Category with Minimum Target |
| Matrix | `pivotTable` | Rows: Category • Columns: Date hierarchy • Values: Total Sales, Total Target |
| Map | `map` | City (Location) • Total Sales (Size) |
| Tree Map | `treemap` | Sub-Category (Group) • Total Sales (Values) |
| Funnel Chart | `funnel` | State (Category) • Order count (Y) |

## 🧮 Key Measures (DAX)

The following measures are used across the visuals (defined in the model — open the file in Power BI Desktop to view/edit the actual DAX formulas, since the compiled data model isn't human-readable outside the app):

- `Total Sales` — *Order Details*
- `Order count` — *Order Details*
- `Max Profit Margin` — *Order Details*
- `Total Target` — *Sales target*
- `Minimum Target` — *Sales target*

## 🛠️ Requirements

- Power BI Desktop (recommended: a recent 2026 build, since the report was authored against the Fluent2 theme released in that cycle)

## ▶️ How to Use

1. Open `DAX___Data_visualization.pbix` in Power BI Desktop.
2. Explore the **Model** view to inspect table relationships.
3. Click through each report page (tabs at the bottom) to see the corresponding DAX measures feeding each visual type.
4. Use this file as a reference/practice template for building similar DAX-driven dashboards.

## 📌 Notes

- This appears to be a **learning/practice file** covering the standard set of core Power BI visuals (column, donut, line, scatter, card, matrix, map, treemap, funnel) paired with DAX aggregation and target-tracking measures.
- No Power Query (M) transformation steps were inspected here — this README focuses on the report/model structure only.
