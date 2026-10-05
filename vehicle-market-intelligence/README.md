# Vehicle Market Intelligence Dashboard
### Mohammed Rafi Shaik · AI-assisted analytics portfolio

An interactive vehicle-listing dashboard created using **Claude AI and basic prompts**. This project demonstrates using an AI assistant to turn an analytics idea into a browser-based dashboard, with pricing, inventory, depreciation, condition, and sale-status views.

**My contribution:** I used Claude AI and prompts to create this dashboard and selected it as a portfolio project. Claude assisted with the implementation. This portfolio describes the supplied artifact; it does not claim that I independently wrote all the JavaScript or performed production deployment.

## Project at a glance

| Item | Detail |
|---|---|
| Full supplied dataset | 100,000 rows × 437 columns |
| Visualizations | 10 charts |
| KPI cards | 5 |
| Filters | Make, body type, fuel, condition, region, seller, date range |
| Implementation | HTML, CSS, JavaScript, Chart.js 4.4.1, SheetJS 0.18.5 |
| Data loading | Local CSV, XLSX, or XLS upload; first worksheet only |
| Starting view | 1,500 randomly generated demo rows |

[Open the dashboard source](dashboard.html) · [Read the chart guide](CHART_GUIDE.md) · [Try the sample CSV](data/cars_sample.csv)

## Run the dashboard

1. Download this project folder and open `dashboard.html` in a modern browser.
2. Keep an internet connection available: Chart.js and SheetJS load from CDN URLs.
3. Click **Upload Excel / CSV** and select `data/cars_sample.csv`, or your full `cars_dataset.csv`.
4. Choose dropdown/date filters, or click a supported chart category to filter the other views.
5. Click **Reset filters** to return to all uploaded rows.

GitHub displays HTML source rather than executing the dashboard. This repository does not currently provide a hosted dashboard URL.

## Verified dataset snapshot

These statistics were calculated from the full supplied CSV, rather than the dashboard’s random demo data:

| Measure | Result |
|---|---:|
| Listing count | 100,000 |
| Mean listing price | 20,608.50 |
| Mean days on market | 38.20 (98,000 populated rows) |
| Mean recorded depreciation | 56.03% (99,000 populated rows) |
| Sold-status share | 34.82% |
| Largest make by listing count | Toyota: 13,085 listings (13.085%) |
| Listing date range | June 2, 2024 – January 15, 2026 |

The price currency is not established by dataset provenance. The dashboard displays dollar symbols. Mean recorded depreciation above excludes missing values; the dashboard can fill missing depreciation using MSRP and listing price, so its displayed result may differ.

## Features and analysis

Five cards show total listings, average listing price, average days on market, sold-status share (labeled sell-through rate), and average depreciation. Ten charts cover monthly listings/prices, makes, fuels, body-type prices, mileage, age/depreciation, condition/time on market, quality scores, price bands, and sale outcomes.

Rule-based summaries recalculate after filtering: largest make, body-type price spread, price correlations with mileage/age, age/depreciation endpoints, average days on market by fuel, accident-history price comparison, seller sold-status share, and depreciation by make (minimum 10 rows).

These summaries are descriptive calculations in JavaScript, not live Claude analysis or a predictive model. For detailed chart labels, calculations, and interactions see [CHART_GUIDE.md](CHART_GUIDE.md).

## Data and interpretation limits

- Dataset source, license, currency, and whether records are real or synthetic have not been established. Treat this as an exploratory learning project, not verified market research.
- The sample contains the **first 100 rows and 22 dashboard-relevant fields**. It is a convenience sample, not a representative statistical sample.
- The full CSV is approximately 233 MB and is omitted from this GitHub project. Large uploads may strain browser memory; start with the sample.
- Missing numeric values are generally excluded from averages. Some fields have fallbacks documented in the chart guide.
- Sold-status share is a snapshot proportion, not a time-normalized conversion metric.
- Average days on market includes populated values across statuses, so the generated phrase “sell fastest” does not establish actual sale speed.
- Correlation and unadjusted accident comparisons do not establish causation. Make, age, and vehicle mix can confound comparisons.
- The radar plots at most five fuel categories; sale outcomes plot the six largest body categories; scatter points are sampled for rendering.
- The supplied HTML is preserved. Imported labels are inserted into HTML without sanitization, so use trusted files. Browser interactions have not been end-to-end tested for this portfolio publication.

## Skills demonstrated

AI-assisted prototyping · Prompt-based development · KPI selection · Interactive data visualization · Exploratory analysis · CSV/Excel workflows · Clear analytics documentation

## Portfolio description

> Created an AI-assisted Vehicle Market Intelligence Dashboard using Claude AI and basic prompts. The browser-based project includes 10 interactive charts, five KPI cards, CSV/Excel upload, and category/date filtering to explore vehicle pricing, depreciation, condition, and sale outcomes. Documented a supplied dataset of 100,000 rows and 437 columns, including its analytical limitations.
