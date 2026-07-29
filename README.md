# Flight Status Dashboard (Power BI)

A Power BI dashboard analyzing US domestic flight status — on-time, delayed,
and cancelled flights — across airlines, airports, and cancellation reasons.

## Data Source & Credits

- **Dataset & Course:** [Maven Analytics](https://www.mavenanalytics.io/) —
  both the flight dataset and the Power BI tutorial followed for this
  project were sourced from Maven Analytics.
- Note: the full Flights dataset exceeds GitHub's 100MB file size limit
  (1M+ rows). A random 10,000-row sample is included in this repo for
  demonstration; the dashboard itself was built and tested against the
  full dataset in Power BI Desktop.

## Data Model

Four tables, structured as a fact table + three dimension tables:
- **Flights** (fact table) — individual flight records with origin,
  destination, airline, and delay/cancellation data
- **Airlines** — IATA airline codes mapped to full airline names
- **Airports** — IATA airport codes mapped to airport names, cities, and coordinates
- **Cancellation Codes** — cancellation reason codes mapped to full descriptions

Relationships built between Flights and each dimension table (via IATA
codes) so visuals display readable names instead of raw codes.

## Transformations (Power Query)

- Promoted headers and verified data types across all four tables
- Removed unnecessary columns from the Flights table
- Added a conditional column, **Status**, classifying each flight as
  Delayed, On-Time, or Cancelled

## DAX Measures

- Total Cancelled Flights, Total On-Time Flights, Total Delayed Flights
- % Cancelled, % Delayed, % On-Time

## Dashboard Features

- KPI cards: Total Flights, Delayed Flights, Cancelled Flights (each with
  a trend line chart)
- Total Flights by City
- % of Delayed Flights by Airline
- Cancelled Flights by Cancellation Description
- Total Flights by Status

## Tools Used

Power BI Desktop — Power Query (data transformation), data modeling
(relationships), DAX measures, visual design/formatting

## Acknowledgments

Built with guidance from Claude (Anthropic) for data modeling structure,
DAX measure planning, and troubleshooting.
