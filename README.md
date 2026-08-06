# LAB IQ — Multi-Branch Laboratory Analytics

A seven-dashboard Tableau reporting suite built for **LAB IQ**, a national laboratory
network operating 25+ branches. The suite gives doctors, branch managers, and
network executives a single governed reporting layer, with each seeing only the
data their role should have access to, covering turnaround time (TAT), sample
acceptance, approval automation, and workload across the network.

> All data shown in these dashboards is synthetic. No real patient, provider, or
> branch-identifying information is included.

---

## The Challenge

LAB IQ processes over **12.9 million tests a year** across routine and urgent
workflows, spread across 25+ branches. Each branch had visibility into its own
numbers, but there was no consolidated way to compare turnaround time, sample
rejection patterns, or workload across the network, and reporting access needed
to respect a strict clinical hierarchy:

- **Doctors**: only see their own patients' data
- **Branch managers**: only see their own branch's operational metrics
- **Overall / senior managers**: need full network-wide visibility to benchmark
  branches and catch systemic bottlenecks

All from the same underlying data model, without maintaining separate dashboards
per role.

## Approach

- Built on top of the laboratory information system, modeled around the metrics
  that drive day-to-day operational decisions: TAT vs. target, sample
  acceptance/rejection, approval automation rate, and workload distribution.
- **Row-level security** implemented so a single published data source powers all
  three access tiers, with no duplicated dashboards and no manual per-branch exports.
- TAT tracked at both a daily and hourly resolution (heatmap views) to surface
  bottlenecks that a daily average would hide.
- Rejection analysis broken out by reason *and* referring source, so branches can
  prioritize the highest-impact fix first rather than chasing every rejection
  equally.

## Dashboards in This Suite

| Dashboard | What it covers |
|---|---|
| **Approval Analysis** | Automated vs. manual approval rates, by test group and urgency, plus approval-time trends by weekday/hour |
| **Laboratory Comparison** | Side-by-side branch benchmarking on TAT, test volume, and target attainment |
| **Sample Acceptance Analysis** | Sample rejection rate, rejection reason, and rejection source, tracked against a network-wide target |
| **TAT Analysis** | Turnaround time vs. routine/urgent targets, with per-test breakdown |
| **TAT Detail Analysis** | Hourly/daily TAT heatmaps and realization-rate trends |
| **Duration Comparison** | Month-over-month TAT trends and delay-rate trends by test group |
| **Workload Analysis** | Test volume by branch, test group, referring institution, and time of day |

## Key Results

| Metric | Value |
|---|---|
| Tests processed | 12.9M+ |
| Branches unified under one reporting layer | 25+ |
| Routine TAT target met | 99.2% |
| Urgent TAT target met | 94.4% |
| Sample rejection rate | ~1.2% |
| Role-based access tiers | 3 (doctor / branch manager / overall manager) |

## Data Model

Built on a set of dimension and fact tables feeding a shared published data source,
with row-level security applied on top so the same model serves all three roles.

## Tech Stack

`Tableau` · `Row-Level Security` · `Multi-Branch Reporting` · `TAT / SLA Analytics` · `Laboratory Information System` · `SQL`

## Repository Contents

```
/assets        → dashboard screenshots (synthetic data only)
README.md      → this file
```

## Links

- Full case study write-up: [ortensa-adhamidhi.github.io/labiq.html](#)
- Portfolio: [ortensa-adhamidhi.github.io](#)

---

© 2026 Ortensa Adhamidhi — Senior Data Analyst & Analytics Engineer
