# 01 — Basic IP Geolocation Lookup

## Overview

Look up one public IPv4 or IPv6 address through IP2Location.io and inspect its location, ASN, and other returned JSON fields.

## Files

Keep these files in the **same directory**:

- `01_ip2locationio_basic_ip_lookup.ipynb`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests
```

Open the notebook interactively:

```bash
python -m jupyter lab "01_ip2locationio_basic_ip_lookup.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_01.ipynb "01_ip2locationio_basic_ip_lookup.ipynb"
```

## Configuration and output

Set `IP_ADDRESS` in the configuration cell (defaults to `8.8.8.8`). This notebook always performs a **live API request**; there is no offline demo mode.

Lookup details and the full JSON response appear in the notebook; no CSV is written.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

An internet connection is required.

API reference: https://www.ip2location.io/ip2location-documentation
