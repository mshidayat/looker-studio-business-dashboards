# Looker Studio Business Dashboards — Case Study

**Role:** Manager Product & Insight · **Tools:** Looker Studio · BigQuery · SQL · Google Sheets
**Products covered:** 4 B2B e-commerce products in one reporting system (order platform, logistics, inventory, academy)

> ⚠️ **Sanitized case study.** This repository describes the structure, process, and lessons from dashboards I built for management reporting. All figures are **indexed (previous period = 100)** — no real company data, client names, or dashboard links/screenshots from the internal system are published here.

## 🎯 The Problem
Management reviewed performance across 4 products, but numbers lived in separate places:
- Monthly reviews relied on manual recaps that took days and often disagreed with each other
- No single view of **target vs achievement** per product and per business group
- When performance dropped, it was unclear *why* — price/margin, volume, or a few big accounts

## 🛠️ What I Built
A Looker Studio dashboard system used for daily/monthly management reporting, with pages for:

| Page | Purpose |
|---|---|
| Target & Achievement | KPI vs target per product and per business group |
| Monthly Performance | Current month + last-3-months trend |
| Acquisition | New-user / new-merchant acquisition performance |
| Revenue Breakdown | Internal vs external revenue split |

**Design principles:** one KPI definition per metric everywhere · every total reconcilable to its source · built for a 5-minute management read (headline first, detail below).

### Spotlight: Ocademy (learning platform)
For Ocademy I built a dedicated Looker Studio dashboard to monitor performance and key business metrics for management reporting. Alongside it, I optimized the data server configuration and usage behind the platform — **successfully reducing data server costs while keeping data services and reporting reliable**. Cost efficiency and reporting quality were treated as one problem: cheaper infrastructure is only a win if the numbers on the dashboard stay trustworthy.

## 🔍 Process
1. **Concept** — start from the decisions management must make each month, not from available charts
2. **Validation** — re-pull and reconcile totals across *all* dashboard pages before trusting any of them
3. **Analysis** — trend, target achievement per group, driver and concentration analysis
4. **Insight** — short, actionable narrative for leadership, with a recommendation

## 💡 Example Finding (indexed, sanitized)
A monthly performance review first looked like a pricing problem. After validation and driver analysis:

| Metric | Index (prev. month = 100) |
|---|---|
| Transaction value | 96 |
| Revenue | 95 |
| Margin rate | 99 |

- Transaction value and revenue fell ±5% while margin stayed flat → **a volume problem, not a margin problem**
- Target achievement split sharply by team: one group at ±130%, another at ±84%
- One account drove ±70% of the month's decline; the top-10 accounts were ≈ half of total value → **concentration risk**
- Totals differed ±1–6% between dashboard pages → recommendation: **designate one page as the single source of truth**

## 📈 Impact
- One dashboard system for daily/monthly/annual management reviews across 4 products
- KPI target monitoring per business group in a single view
- Data-validation step became a standing part of the reporting framework — numbers are reconciled *before* they reach decision-makers

## 🧠 Lessons
- A dashboard is only as good as its validation process — unreconciled pages quietly create wrong decisions
- Indexing and rounding let you publish honest case studies without leaking a single confidential figure
- The most valuable output is rarely the chart; it is the one-sentence answer to "so what do we do?"

## 🔜 Recreate It Yourself
The same structure can be rebuilt on public/dummy data: connect a sample e-commerce dataset in BigQuery → build the 4 pages above in Looker Studio → apply the validation checklist in `VALIDATION.md`.
