# 08 — International Marketing Campaign Scheduling

## Overview

Plan campaign delivery at local weekday business hours using IP geolocation, named IANA time zones, and daylight-saving-aware UTC conversions.

## Files

Keep these files in the **same directory**:

- `08_ip2locationio_international_campaign_scheduling.ipynb`
- `sample_campaign_audiences.csv`

## Run from a terminal

Requires **Python 3.9+**. Open a terminal in the directory containing the notebook and sample files. Install the dependencies:

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib tzdata
```

Open the notebook interactively:

```bash
python -m jupyter lab "08_ip2locationio_international_campaign_scheduling.ipynb"
```

Alternatively, execute **every cell** without opening a browser and save a copy with outputs:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_08.ipynb "08_ip2locationio_international_campaign_scheduling.ipynb"
```

## Configuration and output

`MODE = "demo"` uses offline fixtures and a fixed planning date. `MODE = "live"` queries the API and uses the current UTC time. Use `timezone_override` for a verified IANA time zone if the response lacks one.

Creates `outputs_notebook_08/campaign_schedule.csv`, `campaign_review_queue.csv`, `campaign_market_summary.csv`, and `campaign_utc_dispatch.csv`.

For **authenticated API requests**, set `IP2LOCATION_API_KEY` in the *same terminal* **before** starting Jupyter or executing the notebook (optional for supported keyless lookups):

- **Windows PowerShell:** `$env:IP2LOCATION_API_KEY="YOUR_API_KEY"`
- **macOS / Linux:** `export IP2LOCATION_API_KEY="YOUR_API_KEY"`

This notebook **plans** send times; it does not send messages. `tzdata` is useful for Windows systems that lack IANA zone data. Offset-only responses are not assumed to be DST-safe.

API reference: https://www.ip2location.io/ip2location-documentation
