# 09 — Geofencing and Regional Access Policies

## Overview

Apply illustrative country and region access rules to visitors and produce auditable ALLOW, DENY, or REVIEW decisions using geolocation.

## Files

Keep these files in the **same directory**:

- `09_ip2locationio_geofencing_regional_access_control.ipynb`
- `sample_geofencing_visitors.csv`
- `sample_geofencing_policies.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "09_ip2locationio_geofencing_regional_access_control.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_09.ipynb "09_ip2locationio_geofencing_regional_access_control.ipynb"
```

## Configuration and output

`MODE = "demo"` is offline with synthetic locations. Switch to `"live"` for actual IP2Location.io queries. Edit the policies CSV to change access rules.

Creates `outputs_notebook_09/geofencing_visitor_decisions.csv`, `geofencing_policy_summary.csv`, `geofencing_review_queue.csv`, and `geofencing_reason_summary.csv`.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

Both input CSVs are required beside the notebook. This is a **policy evaluation report**, not an enforcement server. IP location is approximate and should not be your only check for legal or high-impact access restrictions.

API reference: https://www.ip2location.io/ip2location-documentation
