# 02 — Batch IP Geolocation from CSV

## Overview

Read IP addresses from a CSV, validate and deduplicate them, enrich public IPs using the standard API endpoint, and retain all original rows.

## Files

Keep these files in the **same directory**:

- `02_ip2locationio_csv_batch_lookup.ipynb`
- `sample_ips.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas
```

Open the notebook interactively:

```bash
python -m jupyter lab "02_ip2locationio_csv_batch_lookup.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_02.ipynb "02_ip2locationio_csv_batch_lookup.ipynb"
```

## Configuration and output

Input: `INPUT_CSV = "sample_ips.csv"`. Change `MAX_UNIQUE_LOOKUPS` (default `25`) only after checking your API quota. This notebook always performs **live API requests**, not simulated lookups.

Creates `ip_geolocation_results.csv` in the current working directory.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

Put the input CSV beside the notebook. If it is missing, the notebook can generate a small example CSV.

API reference: https://www.ip2location.io/ip2location-documentation
