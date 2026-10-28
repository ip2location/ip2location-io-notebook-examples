# 10 — Network and ISP Intelligence

## Overview

Analyze traffic by ASN, autonomous system, ISP, and available network usage type; summarize requests, unique IPs, and bytes transferred.

## Files

Keep these files in the **same directory**:

- `10_ip2locationio_network_isp_intelligence.ipynb`
- `sample_network_traffic.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib
```

Open the notebook interactively:

```bash
python -m jupyter lab "10_ip2locationio_network_isp_intelligence.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_10.ipynb "10_ip2locationio_network_isp_intelligence.ipynb"
```

## Configuration and output

`MODE = "demo"` provides synthetic network details offline. Set `MODE = "live"` to query the API; `MAX_UNIQUE_LOOKUPS` limits distinct IP requests.

Writes eight CSV reports to `outputs_notebook_10/`, including `network_traffic_enriched.csv`, `network_segment_summary.csv`, `network_asn_summary.csv`, `network_isp_summary.csv`, and `network_field_coverage.csv`.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

ISP and usage classifications may require a paid plan. Missing ISP information is not inferred from the AS operator. Network classifications are descriptive, not proof of abuse.

API reference: https://www.ip2location.io/ip2location-documentation
