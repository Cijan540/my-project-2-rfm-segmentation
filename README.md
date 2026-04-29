# Customer Segmentation & RFM Analysis — Austin Airbnb Host Portfolio

Customer segmentation of 4,829 active Austin Airbnb hosts using RFM analysis and K-Means clustering. The project treats **hosts as Airbnb's customers** in a two-sided marketplace framing and produces a prioritized set of retention, growth, and marketplace-cleanup recommendations grounded in 10,402 listings of operational data.

---

## Headline Findings

- **19% of hosts generate 60.8% of all marketplace revenue.** The Champions segment drives the majority of platform economics in Austin.
- **45% of hosts generate 84% of revenue** at the broader K-Means cluster level — the "Engine" cluster is the operational core of the marketplace.
- **120 hosts represent the highest-priority retention opportunity** — Engine-tier hosts flagged as At Risk or Cannot Lose Them, holding $2.89M in trailing-year revenue. Full list exported as `outputs/retention_priority_list.csv`.
- **Superhost concentration tracks revenue concentration almost perfectly.** Segments with 70%+ Superhost rates generate 86.8% of all revenue.
- **497 hosts in the Inactive cluster generate $0 in trailing-year revenue** despite carrying the highest average list prices — a marketplace cleanup opportunity.

---

## Key Methodological Choices

- **Hosts as the unit of analysis,** not listings — Airbnb's retention economics operate at the host level.
- **Snapshot-anchored Recency** using the dataset's most recent review date (2025-09-16) rather than today's date, preventing artificial inflation of dormancy values.
- **Log transformation before K-Means** to compress right-tailed RFM distributions. The first attempt without log transformation collapsed 92% of hosts into one cluster — diagnosed and fixed iteratively.
- **Two-stage K selection** combining the elbow method (candidate range) with silhouette score (final pick) for a more defensible K than either technique alone. Final K = 3, silhouette score 0.41.
- **Dual-track segmentation** running rule-based segments (10 groups) and K-Means clusters (3 groups) in parallel, then cross-tabulating to reveal convergence and divergence.

---

## Stack

Python · Pandas · Scikit-learn · Matplotlib · Seaborn

---

## Data Source

`data/listings_clean.csv` — 10,402 Austin Airbnb listings cleaned via the Project 1 pipeline. Source: [Inside Airbnb](http://insideairbnb.com/austin). Snapshot date: September 2025.