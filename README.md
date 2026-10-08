# Netflix Database Analysis

**SQL-Based Business Analytics | Content Strategy, User Engagement & Customer Reviews**

A database analytics project examining Netflix-related content, viewing behavior, search activity, and ratings to develop actionable recommendations for streaming-platform decisions.

**Project team:** Shenghao Ma, Qunfeng Zhou, Chutong Wang  
**Institution:** New York University  
**Report date:** September 12, 2025

[**Read the full business report (PDF)**](./netflix_businessreport.pdf)

## Project Overview

This project uses a relational Netflix-style database to answer business questions across three areas:

1. **Content strategy:** How do movies, TV series, countries, and genres differ in representation and performance?
2. **User behavior and engagement:** How do search activity, subscription plans, devices, and viewing patterns relate to engagement?
3. **Ratings and review quality:** How reliable are star ratings when compared with verified viewing activity?

We use SQL-based data preparation, aggregation, analytical views, and statistical analysis to translate database records into business insights.

## Data Provenance and Transparency

**This is an academic analysis of a simulated Netflix ecosystem, not an analysis of Netflix's confidential production systems.** The project report explicitly states that its dataset *simulates* the Netflix content library, user information, watch history, reviews, and search activity.

- Reported metrics and findings are results of the project's analyses of its underlying dataset, rather than invented performance claims.
- **Simulated data should not be represented as authenticated, real Netflix customer-level data.** The original source and provenance of each underlying table are not established by the report alone.
- All findings and recommendations describe patterns **within the analyzed dataset** and should not be treated as independently verified facts about Netflix's live operations.
- The full report includes SQL queries and view definitions that document the analytical approach. The raw source tables are not currently included in this repository.

## Analytical Approach

### Data Preparation

- Standardized genre, country, and content-type fields.
- Addressed invalid or missing values and aligned timestamp formats.
- Converted duration measures to consistent units.
- Built derived features, including Netflix Original indicators, viewing metrics, and search frequency.
- Created reusable SQL analytical views.

### Composite Performance Metrics

The analysis designed two weighted scores using the Analytic Hierarchy Process (AHP) as a weighting framework. Component measures are normalized where specified in the SQL.

**Content Performance Score (CPS)** evaluates titles using:

```text
CPS = 0.60 × Rating + 0.25 × Watch Time + 0.15 × Verified Review Ratio
```

**User Engagement Score (UES)** evaluates users using:

```text
UES = 0.65 × Watch Minutes + 0.25 × Device Diversity + 0.10 × Search Activity
```

These are project-defined analytical scores, not official Netflix KPIs.

## Selected Findings

The following figures are **results reported for the project dataset**:

| Area | Finding |
| --- | --- |
| Content | Movies dominate catalog counts, while TV series feature prominently among high-CPS titles. |
| Runtime vs. ratings | The reported linear regression found essentially no explanatory relationship (R² ≈ 0.00007; p = 0.2989). |
| Search | Across 25,000 search events, 22,562 were associated with at least one viewing session, a reported search-to-watch conversion rate of 90.25%. |
| Search experience | 1.1% of searches returned zero results; approximately 73% used no filters. |
| Completion | Average title completion rates clustered around 55–60% in the analysis. |
| Review quality | Among the extreme (1-star and 5-star) ratings analyzed, 83.5% were 5-star; 99.7% of 5-star reviews were classified as unverified under the project's rule. |

Interpret these findings in the context of the model assumptions and the dataset's simulated nature. In particular, observational patterns should not be read as causal proof.

## Business Recommendations

- **Content investment:** Evaluate title performance across ratings, viewing behavior, and completion rather than relying on runtime or genre alone.
- **Content discovery:** Investigate unsuccessful and low-conversion search queries; improve search suggestions and metadata.
- **User experience:** Prioritize device-specific improvements informed by observed viewing patterns.
- **Review integrity:** Combine star ratings with verified-view and behavioral signals before making content decisions.
- **Retention:** Identify titles with both strong CPS and completion rates for deeper investigation.

## Tools and Skills Demonstrated

- **SQL:** relational joins, common table expressions (CTEs), window functions, aggregation, views, conditional logic, and metric construction
- **Data cleaning and modeling:** standardization, validation, derived attributes, and integrated tables
- **Statistical analysis:** regression and interpretation of significance
- **Business analytics:** KPI design, user segmentation, content performance, and decision-oriented recommendations
- **Data visualization and communication:** charts, result tables, and written business reporting

## Repository Contents

```text
Netflix-Database-Analysis/
├── README.md
└── netflix_businessreport.pdf
```

The PDF contains the project's data model, analysis, charts, conclusions, recommendations, and a SQL appendix.

## Contributors

- Shenghao Ma
- Qunfeng Zhou
- Chutong Wang

*Academic portfolio project. Not affiliated with, endorsed by, or based on internal access to Netflix.*
