# 06 — Website Content Localization

## Overview

Suggest a visitor-facing language, currency, and market using IP geolocation, while prioritizing explicit visitor preferences.

## Files

Keep these files in the **same directory**:

- `06_ip2locationio_website_content_localization.ipynb`
- `sample_localization_visitors.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "06_ip2locationio_website_content_localization.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_06.ipynb "06_ip2locationio_website_content_localization.ipynb"
```

## Configuration and output

`MODE = "demo"` uses synthetic locations offline. Switch to `"live"` to use the API. Configure `INPUT_CSV` and mapping rules in the notebook as needed.

Creates `outputs_notebook_06/visitor_localization_results.csv` and `localization_summary.csv`.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

Language and currency defaults are suggestions; actual prices and exchange rates are not fetched. Some API metadata depends on your plan.

API reference: https://www.ip2location.io/ip2location-documentation
