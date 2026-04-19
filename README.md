# Project 2: Customer Segmentation & RFM Analysis

## Business Context
Airbnb operates as a two-sided marketplace where **hosts are customers** — they supply inventory, pay service fees, and can churn to competitors. This project segments Austin Airbnb hosts using RFM analysis and K-Means clustering to identify:

- **Champions** — top hosts driving marketplace value
- **At-Risk hosts** — valuable hosts showing signs of churn
- **Growth opportunities** — hosts with potential to scale

## Methodology
1. **RFM Analysis** — Recency, Frequency, Monetary scoring of hosts
2. **Quintile scoring** — 1–5 buckets per dimension
3. **Rule-based segmentation** — classic RFM segment labels
4. **K-Means clustering** — data-driven segment discovery
5. **Silhouette analysis** — optimal cluster count selection

## Stack
Python · Pandas · Scikit-learn · Matplotlib · Seaborn

## Data
Source: `listings_clean.csv` (from Project 1 — Austin Airbnb Pricing Intelligence)
10,402 listings across Austin, TX, aggregated to host level.

## Outputs
See `/outputs` for segment assignments, RFM scores, and IBCS-compliant visualizations.
