# Submission README

## Track Chosen
Fictional Domain Packet

## What I Built
An data analysis Jupyter Notebook that cleans raw telemetry logs and engineers key metrics (e.g., weighted acceptance rates, flag rates) to answer two core questions: *Which workflow is most useful right now?* and *Did system changes help, hurt, or create uncertainty?*

## Who It Is For
Product Managers and AI Platform Engineers evaluating generative AI workflow performance

## Data Or Source Used
`product_usage_events.csv`

## Assumptions I Made
* **Weighted Metric Aggregation:** Evaluated acceptance rates using weighted volume ($\sum \text{accepted} / \sum \text{completed}$) rather than simple daily averages to prevent low-volume entries from skewing performance.
* **Missing Data Imputation:** Imputed missing confidence scores using workflow-specific medians, while preserving missing subjective user ratings as `NaN`.
* **Noise Isolation:** Flagged and excluded the August 5 demo spike (140 sessions) to protect baseline organic trends.

## Data Issues Or Caveats I Noticed
* **Data Quality Flaws:** Un-normalized team casing (`product`), duplicate export logs (Aug 5), missing values, and a sudden drop in logging `manual` entry sources on Aug 7.
* **Operational Impact:** The Aug 4 prompt update **helped** (Lead Summary acceptance rose to 85.7%), while the Aug 7 review policy **hurt** Support's `Reply draft` (flag rate spiked to 70.6%; rating fell to 2.1).
* **Top Workflow:** **Lead Summary (Sales)** is currently most useful, combining highest usage with an 82.4% weighted acceptance rate.

## What I Would Do Next With More Time
* Build an interactive Streamlit dashboard to slice performance across integrated vs. manual input sources.
* Implement automated data validation schemas (Pydantic/dbt) to catch duplicate exports and missing fields upstream.
