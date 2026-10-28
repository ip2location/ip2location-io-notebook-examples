# 04 — VPN, Proxy, and Tor Detection

## Overview

Review IP addresses for available VPN, Tor, proxy, data-center, and threat signals, then produce a security-review table.

## Files

Keep these files in the **same directory**:

- `04_ip2locationio_vpn_proxy_tor_detection.ipynb`
- `sample_security_ips.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "04_ip2locationio_vpn_proxy_tor_detection.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_04.ipynb "04_ip2locationio_vpn_proxy_tor_detection.ipynb"
```

## Configuration and output

`MODE = "demo"` runs on explicitly synthetic responses, with no API calls. Change it to `"live"` for real IP lookups. The IP input column is `ip_address`.

Creates `04_ip2locationio_security_review.csv` and `04_ip2locationio_security_summary.csv`.

For **authenticated API requests**, set `IP2LOCATION_IO_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_IO_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_IO_API_KEY="YOUR_API_KEY"`

Some detection fields require a higher subscription; unavailable fields are not the same as negative detection. The notebook uses `IP2LOCATION_IO_API_KEY` (note the `_IO_`).

API reference: https://www.ip2location.io/ip2location-documentation
