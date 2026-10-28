# 03 — Website Visitor Geolocation from Access Logs

## Overview

Extract and validate IP addresses from Apache/Nginx Common or Combined access logs, look up unique public IPs, and chart traffic by geography.

## Files

Keep these files in the **same directory**:

- `03_ip2locationio_website_visitor_geolocation.ipynb`
- `sample_access.log`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "03_ip2locationio_website_visitor_geolocation.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_03.ipynb "03_ip2locationio_website_visitor_geolocation.ipynb"
```

## Configuration and output

Input: `INPUT_LOG = "sample_access.log"`. `MAX_UNIQUE_LOOKUPS` defaults to `20`. This notebook uses **live API requests** and an internet connection.

Creates `website_visitors_geolocated.csv` and displays charts and summary tables.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

If the example log is absent, the notebook can create one. For real logs, make sure your server records the true client IP from trusted proxies; do not assume every source IP represents a visitor.

API reference: https://www.ip2location.io/ip2location-documentation
