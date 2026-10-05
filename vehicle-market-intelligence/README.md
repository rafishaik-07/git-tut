# Vehicle Market Intelligence Dashboard
### Mohammed Rafi Shaik · AI-assisted analytics portfolio

An interactive vehicle-listing dashboard created using **Claude AI and basic prompts**. This project demonstrates using an AI assistant to turn an analytics idea into a browser-based dashboard, with pricing, inventory, depreciation, condition, and sale-status views.

**My contribution:** I used Claude AI and prompts to create this dashboard and selected it as a portfolio project. Claude assisted with the implementation. This portfolio describes the supplied artifact; it does not claim that I independently wrote all the JavaScript or performed production deployment.

## Run the dashboard

Download `dashboard.html` and open it in a modern browser with an internet connection. Click **Upload Excel / CSV** to load your own trusted file. The initial view uses random demo data. Choose category/date filters or click supported chart categories. Use **Reset filters** to restore all rows.

GitHub displays source rather than running HTML. No hosted dashboard URL is configured. Uploaded dataset records and statistics are excluded from this public portfolio pending explicit permission.

## Features and analysis

Five cards show total listings, average listing price, average days on market, sold-status share (labeled sell-through rate), and average depreciation. Ten charts cover monthly listings/prices, makes, fuels, body-type prices, mileage, age/depreciation, condition/time on market, quality scores, price bands, and sale outcomes.

Rule-based summaries recalculate after filtering: largest make, body-type price spread, price correlations with mileage/age, age/depreciation endpoints, average days on market by fuel, accident-history price comparison, seller sold-status share, and depreciation by make (minimum 10 rows).

These summaries are descriptive calculations in JavaScript, not live Claude analysis or a predictive model. For detailed chart labels, calculations, and interactions see [CHART_GUIDE.md](CHART_GUIDE.md).

## Data and interpretation limits

- Dataset source, license, currency, and whether records are real or synthetic have not been established. Treat this as an exploratory learning project, not verified market research.
- Missing numeric values are generally excluded from averages. Some fields have fallbacks documented in the chart guide.
- Sold-status share is a snapshot proportion, not a time-normalized conversion metric.
- Average days on market includes populated values across statuses, so the generated phrase “sell fastest” does not establish actual sale speed.
- Correlation and unadjusted accident comparisons do not establish causation. Make, age, and vehicle mix can confound comparisons.
- The radar plots at most five fuel categories; sale outcomes plot the six largest body categories; scatter points are sampled for rendering.
- The supplied HTML is preserved. Imported labels are inserted into HTML without sanitization, so use trusted files. Browser interactions have not been end-to-end tested for this portfolio publication.

## Skills demonstrated

AI-assisted prototyping · Prompt-based development · KPI selection · Interactive data visualization · Exploratory analysis · CSV/Excel workflows · Clear analytics documentation

## Portfolio description

> Created an AI-assisted Vehicle Market Intelligence Dashboard using Claude AI and basic prompts. The browser-based project includes 10 interactive charts, five KPI cards, CSV/Excel upload, and category/date filtering to explore vehicle pricing, depreciation, condition, and sale outcomes. Documented chart calculations and analytical limitations.

