# Dashboard Validation Checklist

Run before any dashboard numbers are used in a management report:

1. **Cross-page reconciliation** — the same metric must show the same total on every page; log any difference and find its cause (filter, date field, data source) before publishing
2. **Source check** — re-pull the metric from its source (BigQuery / database / sheet) and compare with the dashboard total
3. **Date-range check** — confirm every chart uses the same period, timezone, and "last updated" timestamp
4. **Definition check** — one agreed definition per KPI (what counts as revenue, transaction, active user); document it on the page
5. **Outlier check** — the top accounts/drivers behind any big movement must be identifiable; a headline number dominated by one account or an unrelated topic must be flagged, not reported raw
6. **Single source of truth** — if pages disagree and cannot be reconciled in time, designate ONE page as official for that review and note it in the report
