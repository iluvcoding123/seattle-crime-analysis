# Seattle Transit Safety: Spatiotemporal Risk Analysis (2021–2026)
*By Justin Kim*

## 1. Executive Summary
This project provides an "Operational Intelligence" framework designed for transit agencies to optimize security and ambassador deployments. By performing a spatial join between 1.5 million Seattle Police Department (SPD) crime records and King County Metro GTFS infrastructure data, this analysis identifies the highest-risk nodes in the transit network.

**The "Hero Statistic"**: In the post-COVID era (2021–2026), **over 82% of citywide violent crime** occurred within a 150m buffer of a transit stop. While the Northgate Transit Center sees the highest raw volume of incidents, a **Weighted Risk Priority Matrix** identifies **3rd Ave & Pike St** as the highest-severity safety node in the network.

---

## 2. Datasets & Reproducibility
To ensure transparency and reproducibility, this project utilizes two primary open-source datasets:

* **Crime Incident Data**: [SPD Crime Data (2008–Present)](https://data.seattle.gov/Public-Safety/SPD-Crime-Data-2008-Present/tazs-3rd5/about_data) — *Dataset accessed February 2026.*
* **Transit Infrastructure**: [King County Metro GTFS Feed](http://metro.kingcounty.gov/gtfs/) — *Used to map 3,200+ unique stop coordinates.*

*Note: The raw 1.5GB+ CSV is excluded via `.gitignore`. To run locally, download from the links above and place in the `/data` directory.*

---

## 3. Analysis Scope: The "New Normal"
While the raw data spans back to 2008, this study implements a `is_post_covid` flag (Threshold: $\text{Year} \ge 2021$) to focus on current urban recovery trends. This ensures all recommendations are aligned with:
* Post-pandemic ridership shifts.
* The **2026 Operation Safe Transit** initiative.
* The reported **22% reduction in overall King County crime** observed in 2025.

---

## 4. Methodology
1.  **Spatial Buffering**: Engineered a 150-meter radius around all GTFS coordinates to distinguish "Transit-Adjacent" incidents from general city trends.
2.  **Temporal Risk Profiling**: Normalized hourly incident rates to create the **"Rider's Clock"**, identifying peak vulnerability windows for commuters.
3.  **Weighted Severity Modeling**: Developed a risk-scoring system to prioritize person-to-person safety:
    * **Violent Crime**: 5x Multiplier
    * **Society/Drug Offenses**: 3x Multiplier
    * **Property Crime**: 1x Multiplier
4.  **Priority Matrix Synthesis**: Ranked 3,200+ stops to identify the "Critical 5" locations requiring immediate inter-disciplinary intervention.

---

## 5. Key Insights
* **The Afternoon Surge**: Transit-adjacent risk disproportionately outpaces citywide trends during the **13:00–18:00 window**. Conversely, the morning commute (06:00–09:00) remains statistically safer, validating the "Natural Surveillance" theory.
* **High-Incident Hubs**: 10 specific hubs account for nearly **10% of all transit-related risk weight**. Strategic focus on these "Critical Nodes" offers the highest ROI for security budgets.
* **Safety vs. Volume**: Analysis reveals that **3rd Ave & Pike St** is the high-severity leader (Violent Crime), while **Northgate (5th Ave NE)** is the high-volume leader (Property/All Other).

---

## 6. 2026 Operational Recommendations
* **Personnel Shift**: Transition from static morning patrols to agile afternoon deployments (13:00–18:00).
* **Ambassador Integration**: Prioritize the **Top 5 Priority Matrix** locations for the "Transit Ambassador" pilot, as these nodes are driven by high-severity "Person" crimes rather than simple property theft.
* **Infrastructure Synergy**: Align 2026 lighting and CCTV upgrades with the high-risk corridors identified on **2nd Avenue** and the **Pike/Pine corridor**.

---

## 7. Tech Stack
* **Language**: Python 3.13
* **Analysis**: Pandas, NumPy
* **Spatial Logic**: Scipy.spatial (KDTree for proximity), Geopy
* **Visualization**: Matplotlib, Seaborn (Custom "Operational Intelligence" style)