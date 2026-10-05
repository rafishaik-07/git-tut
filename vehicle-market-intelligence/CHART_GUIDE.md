# Chart and KPI guide

## KPI cards

| Display label | Calculation |
|---|---|
| Total listings | Count of currently filtered rows |
| Avg listing price | Mean `listing_price`, falling back to `current_market_price` per row |
| Avg days on market | Mean nonmissing `days_on_market` |
| Sell-through rate | Rows classified as sold / all filtered rows × 100; a status snapshot |
| Avg depreciation | Mean `depreciation_percent`; if absent, `(1 − price / msrp) × 100` when possible |

Sold classification uses a case-insensitive “sold” substring in `sale_status`, or a populated final sale price when status is absent. The supplied dataset's statuses were checked; other uploads could contain “Not Sold”, which this implementation would misclassify.

## All ten visualizations

| # | Dashboard label | Chart and measures | Interaction / interpretation |
|---|---|---|---|
| 1 | Timeline: listings & average price by month | Monthly bar counts plus mean-price line on a second axis; labels: Listings, Avg price | Click month to set date range. Describes listing activity, not completed sales. |
| 2 | Top 10 makes by listings | Horizontal bars, top 10 makes ranked by count | Click make to filter. Inventory share is not verified market share. |
| 3 | Fuel type mix | Doughnut, count by `fuel_type` | Click fuel slice to filter. |
| 4 | Average price by body type | Bars, mean price by body type, descending; label: Avg price | Click body type to filter. Averages depend on vehicle mix. |
| 5 | Price vs odometer (scatter) | X: Odometer (km); Y: Price; dataset label: Vehicle | Only rows with price and odometer; deterministic sampling uses `floor(n / 700)` as step, so 700 is not a strict point cap. |
| 6 | Depreciation % by vehicle age | Filled line of mean depreciation by numeric age; label: Avg depreciation % | Cross-sectional averages, not longitudinal vehicle tracking. |
| 7 | Avg days on market by condition | Bars of mean days by condition; label: Days | Click condition to filter. Includes available and other statuses. |
| 8 | Quality radar by fuel type | Mean Reliability, Safety, Performance, Condition scores | First five encountered fuel categories; underlying score definitions are unknown. |
| 9 | Price distribution (histogram) | 12 price bins, rounded-up bin width based on filtered maximum; label: Listings | Bins change after filtering; dollar/k labels assume a currency not verified by source. |
| 10 | Sale outcome by body type (stacked) | Status counts stacked across top six body types | Counts rather than within-body percentages. |

## Controls and supporting labels

Upload Excel / CSV · Reset filters · Make · Body type · Fuel · Condition · Region · Seller · From · To. The source subtitle reports the active file and row count. The initial label is Demo data. The analysis panel is titled “Deep analysis — auto-generated from the filtered data”.

Column names are trimmed, lowercased, and whitespace becomes underscores. Dates support JavaScript-parsable strings and Excel serial dates. Region falls back to state/province and then country only for null/undefined values. Missing groups are omitted from grouping charts; numeric means exclude missing values. The interface adapts to available category values and system dark mode.

## Rule-based insight labels

Market leader · Price spread · Mileage effect · Depreciation curve · Speed to sell · Accident discount · Channel performance · Best value retention.

The wording comes from the supplied HTML. “Market leader” is the largest make in the uploaded/filtered inventory, “Channel performance” is sold-status share, and “Speed to sell” compares mean days on market across all populated rows. Interpret these as descriptive summaries rather than verified market or causal conclusions.
