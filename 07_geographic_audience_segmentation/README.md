# 07 — Geographic Audience Segmentation for Marketing

## Overview

Enrich marketing session records with IP geolocation and compare country, region, channel, conversions, and revenue to guide market review.

## Files

Keep these files in the **same directory**:

- `07_ip2locationio_geographic_audience_segmentation.ipynb`
- `sample_marketing_sessions.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "07_ip2locationio_geographic_audience_segmentation.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_07.ipynb "07_ip2locationio_geographic_audience_segmentation.ipynb"
```

## Configuration and output

`MODE = "demo"` is offline and uses synthetic geolocation. Change to `"live"` to query IP2Location.io. Adjust `MAX_UNIQUE_IPS` cautiously for larger inputs.

Creates `outputs_notebook_07/` reports: `marketing_sessions_enriched.csv`, `marketing_country_kpis.csv`, `marketing_region_kpis.csv`, `marketing_channel_kpis.csv`, and `marketing_market_review.csv`.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

Sample sessions, conversions, and revenue are synthetic. Geographic differences alone do not prove a campaign caused an outcome.

API reference: https://www.ip2location.io/ip2location-documentation
