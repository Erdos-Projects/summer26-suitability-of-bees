### 26.6.12

Need to produce the following documents:
 - Data acquisition scripts in src/data/: One-off downloads, API calls, scraping scripts, or database query files. Each should log provenance (URLs, queries, timestamps).
 - Raw data snapshot in data/raw/: A small immutable sample, or instructions for secure download if too large/sensitive.
 - Baseline modeling notebook in notebooks/baseline.ipynb:
    - Implements trivial, linear, and tree-based baselines.
    - Evaluates with cross-validation.
    - Reports both primary and secondary KPIs in a table.
 - KPI definition file (kpis.md): Explicit metrics, formulas, and improvement directions.
 - Environment specification (environment.yml or requirements.txt):   Reproducible package list including pandas, numpy, scikit-learn, and any acquisition libraries used.

 > Michael comment - I can write one of these up for a first initial model. Don't know how to generate a GLM for location data yet, but perhaps its just assigning probablity values to each grid element of a geospatial grid.
