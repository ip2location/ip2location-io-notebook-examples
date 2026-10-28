# 05 — Suspicious Login and Impossible-Travel Detection

## Overview

Enrich login records with IP locations, compare consecutive successful logins, and flag unusually fast long-distance travel and country changes for review.

## Files

Keep these files in the **same directory**:

- `05_ip2locationio_suspicious_login_geolocation_fixed.ipynb`
- `sample_login_events.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "05_ip2locationio_suspicious_login_geolocation_fixed.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_05.ipynb "05_ip2locationio_suspicious_login_geolocation_fixed.ipynb"
```

## Configuration and output

`MODE = "demo"` uses synthetic locations; `"live"` queries IP2Location.io. Edit the distance and speed thresholds in the shared configuration cell if needed.

Writes `outputs_notebook_05/login_events_enriched.csv`, `login_travel_alerts.csv`, and `login_user_summary.csv`.

For **authenticated API requests**, set `IP2LOCATION_IO_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_IO_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_IO_API_KEY="YOUR_API_KEY"`

Use the **fixed** notebook filename shown here: it resolves the earlier `GEOGRAPHY_COLUMNS` live-mode error. The notebook uses `IP2LOCATION_IO_API_KEY` (note the `_IO_`). Alerts are investigation leads, not proof of compromised accounts.

API reference: https://www.ip2location.io/ip2location-documentation
