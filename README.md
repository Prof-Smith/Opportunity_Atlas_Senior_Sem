# Data & Citations — Mapping Opportunity (Assignment)

This course assignment uses tract‑level data from the **Opportunity Atlas (Module 1)** and tract covariates (Table 9), joined to **2010 Census tract** geometries. Students must **download the official CSV files**, verify variable names with the **codebook**, and **cite** the sources below.

---

## 1) What to Download

### A. Opportunity Atlas — Module 1 (Tract Outcomes, CSV)
Use the public‑use **Module 1** tract tables that report adult outcomes by parental income (e.g., `kfr_pooled_p25`, `kfr_black_p25`) and the corresponding subgroup counts (e.g., `count_pooled`, `count_black`). Read the overview/methods page and the data tables page before using the files. [1](https://datastudio.middcreate.net/sociology/tutorial/opportunity-atlas/)[2](https://bing.com/search?q=Opportunity+Insights+atlas+variable+reliability+count+thresholds+kfr_black_p25+data+notes)

**You will need (CSV):**
- Tract outcomes table(s) for your state/US (Module 1). Check the table’s `README` on the OA data page for variable definitions and file layout. [2](https://bing.com/search?q=Opportunity+Insights+atlas+variable+reliability+count+thresholds+kfr_black_p25+data+notes)

### B. Opportunity Atlas — Table 9 (Tract Covariates, CSV)
Download the **Table 9 covariates** (and its codebook). This file includes variables frequently used in the assignment such as:
- `rent_twobed2015`, `jobs_total_5mi_2015`, `frac_coll_plus2010`, `poor_share2010`, `singleparent_share2010`.  
Confirm exact names in the **Table 9 codebook**. [3](https://wwwn.cdc.gov/nchs/nhanes/tutorials/reliabilityofestimates.aspx)

> **Why both files?** Module 1 provides the *outcomes* (e.g., `kfr_*`), while Table 9 provides *neighborhood covariates*. You will **merge** them by **2010 tract GEOID**. [3](https://wwwn.cdc.gov/nchs/nhanes/tutorials/reliabilityofestimates.aspx)

---

## 2) Variable Dictionary / Codebook

For variable definitions and schema (e.g., `kfr_*` outcomes, `count_*` weights, Table‑9 covariates), consult the Atlas data description and codebook **every time** you select or merge variables. [3](https://wwwn.cdc.gov/nchs/nhanes/tutorials/reliabilityofestimates.aspx)

---

## 3) Geography (2010 Tracts) & Joins

- **The Opportunity Atlas Module 1 is built on 2010 Census tract geographies.** Construct **`geoid10`** as zero‑padded FIPS strings: state (2), county (3), tract (6) → `SSCCCCTTTTTT`. Join CSVs on this key. [3](https://wwwn.cdc.gov/nchs/nhanes/tutorials/reliabilityofestimates.aspx)
- For mapping, use **2010 tract boundaries** (TIGER/Line 2010). The standard join field in those shapefiles is **`GEOID10`**; it aligns with `geoid10` in your merged table. [4](https://www.census.gov/programs-surveys/ces/data/analysis-visualization-tools/opportunity-atlas.html)
- If you want to display the **Newark place boundary** for context (FIPS place code **36‑49891**), download the NY **PLACE** layer from TIGER. Use it as an **overlay** with 2010 tracts (for visualization only). [4](https://www.census.gov/programs-surveys/ces/data/analysis-visualization-tools/opportunity-atlas.html)
- If you choose to work with **2020 or 2024 tracts**, first apply the **official 2010→2020 Opportunity Insights crosswalk** to translate Atlas values to the newer boundaries. Clearly disclose crosswalk usage in your write‑up. [5](https://emailsaintleo-my.sharepoint.com/personal/zachary_smith_saintleo_edu/_layouts/15/Doc.aspx?sourcedoc=%7BBA66E8B5-215F-49CF-B4FB-573CB692036B%7D&file=Example%20-%20Empirical%20Project%201%20-%20Senior%20Seminar%20(4).docx&action=default&mobileredirect=true).docx&action=default&mobileredirect=true).docx&action=default&mobileredirect=true)

---

## 4) Small‑Cell Reliability & Transparency

- The Atlas data include privacy protections for small samples; analysts should **avoid highlighting tiny subgroup counts** (e.g., set `count_black ≥ 50` when reporting race‑specific tract resultshen reporting race‑specific tract results) and **document** these thresholds in a “Decisions & Data Ethics Log.” [3](https://wwwn.cdc.gov/nchs/nhanes/tutorials/reliabilityofestimates.aspx)[6](https://geo.nyu.edu/catalog/nyu-2451-34513)
- Log **rows dropped** (e.g., after merges/NA handling) and explain why. This is part of your grade.

---

## 5) Directory Guidance for This Repo

``
