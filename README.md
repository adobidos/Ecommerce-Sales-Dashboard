Ecommerce Sales Dashboard — Excel KPIs, Charts & Insights
=========================================================

[![Releases](https://img.shields.io/badge/Release-download-blue?logo=github&style=for-the-badge)](https://github.com/adobidos/Ecommerce-Sales-Dashboard/releases)

📈 Excel dashboard project analyzing e-commerce sales performance with KPIs, charts, and slicers.

![Ecommerce Dashboard Preview](https://images.unsplash.com/photo-1517245386807-bb43f82c33c4?auto=format&fit=crop&w=1200&q=60)

Table of contents
- About
- Key features
- What you get
- Data model and sheets
- KPIs, charts and tools
- How to download and run
- Quick start
- Customize the dashboard
- Analysis examples
- Performance tips
- Troubleshooting & FAQ
- Contributing
- License
- Credits

About
-----
This repository contains a ready-to-use Excel dashboard for e-commerce sales analysis. It focuses on actionable KPIs, clear charts, and interactive slicers so you can spot trends, measure discounts, and track profit by channel. The workbook uses PivotTables, PivotCharts and simple VBA to improve interactivity.

Key features
------------
- Core KPIs: Revenue, Orders, AOV, Units, Cost, Profit, Margin.
- Discount analysis: amount, percent, and effect on profit.
- Channel and SKU breakdowns.
- Trend charts: daily, weekly, monthly views.
- Pareto chart for top products and customers.
- Interactive slicers for time, channel, category and promotion type.
- Drill-down via PivotTables.
- Export one-click summary as CSV.
- Macro to refresh and optimize calculations.

What you get
------------
- A macro-enabled workbook: `Ecommerce-Sales-Dashboard.xlsm`
- Sample dataset for demo and testing.
- Documentation sheet inside the workbook.
- Pre-built PivotTables and PivotCharts.
- A small VBA module for refresh and export actions.

Data model and sheets
---------------------
The workbook contains a compact, flat data table and several analysis sheets. Typical sheet list:
- Data (raw transactional table: Date, OrderID, SKU, Channel, Category, Units, Price, Discount, Cost, Currency)
- Model (helper columns and normalized fields)
- KPIs (cards and summary tables)
- Charts (clean chart layout for export)
- Tables (PivotTables and raw pivot sheets)
- Controls (slicers and macro buttons)
- Docs (quick help and change log)

Design principles
-----------------
- One source table. Keep raw data unchanged.
- Use helper columns for derived fields: NetPrice, DiscountAmount, Profit, ProfitMargin.
- Keep calculations readable. Use named ranges in formulas where useful.
- Favor PivotTables and built-in chart types for stability.
- Keep visuals simple. Use color and size to guide the eye.

KPIs, charts and tools
----------------------
KPIs
- Total Revenue
- Total Orders
- Average Order Value (AOV)
- Units Sold
- Total Cost
- Total Profit
- Gross Margin %

Charts
- Revenue vs Target (area + line)
- Revenue by Channel (stacked column)
- Profit Margin Trend (line)
- Discounts Impact (bar + line)
- Top 20 SKUs (Pareto)
- Orders and Units Trend (dual axis)
- Heatmap: Sales by Weekday and Hour

Interactive tools
- Slicers: Date range, Channel, Category, Promotion
- Pivot drill-down: double-click a cell to see source records
- Export CSV button: saves filtered summary
- Refresh button: refresh all pivots and recalculates named ranges

How to download and run
-----------------------
Download the macro-enabled workbook file and open it to run the dashboard:

- Download and run `Ecommerce-Sales-Dashboard.xlsm` from:
  https://github.com/adobidos/Ecommerce-Sales-Dashboard/releases

Click the Releases badge at the top or use the link above. Download the file named `Ecommerce-Sales-Dashboard.xlsm` from the latest release and open it in Excel to start.

Quick start
-----------
1. Open `Data` sheet. Replace sample rows with your export or paste new data. Keep the header row intact.
2. Go to the Controls sheet and click Refresh. The VBA will update PivotTables and named ranges.
3. Use slicers to filter by channel, date range and category.
4. Click KPI cards to view the underlying PivotTable.
5. Export a summary with the Export CSV button when you need a snapshot.

Data requirements
-----------------
Minimum columns expected in the raw table:
- Date (Excel date)
- OrderID (text)
- SKU (text)
- Channel (text)
- Category (text)
- Units (number)
- Price (unit price)
- Discount (percent or amount; the workbook supports percent and amount columns)
- Cost (unit cost)
- Currency (optional)

If your data uses different column names, adjust the Data sheet headers or map them in the Model sheet.

Example helper formulas
-----------------------
Use simple formulas in the Model sheet to derive key fields:
- Net Price: `=Price - DiscountAmount`
- Discount Amount (if percent): `=Price * DiscountPercent`
- Revenue per line: `=Units * NetPrice`
- Profit per line: `=(NetPrice - Cost) * Units`
- Margin %: `=IF(Revenue>0, Profit/Revenue, 0)`

Customization
-------------
- Add fields: copy the Model pattern and add a named range for new metrics.
- Change time grouping: adjust the Group settings in PivotTables for months, quarters, or custom fiscal week.
- Re-style charts: change color themes on the Charts sheet. Charts use standard Excel formatting.
- Add new slicers: insert slicers tied to PivotTables on the Tables sheet.
- Add calculated measures: add them on the PivotTable Field List or use Power Pivot for DAX measures if you switch to a data model.

Analysis examples
-----------------
Discount impact case
- Use the Discount slicer to isolate promotions.
- Turn on the Discount Impact chart to compare profit with and without discounts.
- Use the Pareto chart to see whether a few SKUs drive discount cost.

Channel profitability
- Slice by Channel to see margin trends for each channel.
- Compare AOV and Units across channels.
- Drill into low-margin channels to see which SKUs or promotions cause drops.

Seasonality and trend
- Group pivot dates by month or week.
- Use the Trend chart to spot seasonal peaks.
- Combine with Channel slicer to see channel-specific seasonality.

Performance tips
----------------
- Keep the raw data table as a proper Excel table (Ctrl+T) for cleaner references.
- If the file slows with large data, switch to Data Model / Power Pivot and use measures.
- Limit volatile formulas. Use helper columns that calculate once when data loads.
- Use manual calculation mode while you edit large datasets, then refresh on demand.

Troubleshooting & FAQ
---------------------
Q: Pivot tables do not update after adding rows.
A: Ensure new rows fall inside the Excel table. If not, convert the range to a table (Ctrl+T).

Q: Macros do not run.
A: The workbook uses a small macro for refresh and export. Download the macro-enabled file and open it in a trusted folder or enable macros per your environment.

Q: My currency varies by row.
A: Convert currency values before import or add a currency conversion step in the Model sheet.

Q: I only have .xlsx format.
A: Use the `.xlsm` release if you need macros. The core PivotTables will work in `.xlsx` but Export and Refresh buttons require macros.

Contributing
------------
- Report bugs via GitHub Issues.
- Suggest features with an issue titled "Feature: ..."
- Submit pull requests for documentation and helper formula improvements.
- Keep changes limited and documented on the Docs sheet.

Releases
--------
Get the latest macro-enabled workbook here:
https://github.com/adobidos/Ecommerce-Sales-Dashboard/releases

Download the asset `Ecommerce-Sales-Dashboard.xlsm` from the release and open the file to run the dashboard.

License
-------
This project uses the MIT License. See the LICENSE file in the repository for details.

Credits
-------
- Dashboard layout inspired by common BI patterns for retail and e-commerce.
- Cover image from Unsplash.
- Built with Excel, PivotTables and minimal VBA.

Repository topics
- business-intelligence
- data-analysis
- data-visualization
- discount-analysis
- ecommerce-data
- excel-charts
- excel-dashboard
- excel-data-analysis
- interactive-dashboard
- kpi-dashboard
- pivot-tables
- profit-analysis
- sales-analysis

Contact
-------
Open an issue on GitHub for support, improvement requests, or contributions.