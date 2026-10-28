# IP2Location.io Jupyter Notebook Examples

A collection of **10 practical Jupyter notebooks** demonstrating how to use the [IP2Location.io API](https://www.ip2location.io/) with Python. The examples cover IP geolocation, website analytics, cybersecurity, content localization, marketing, geofencing, and network intelligence.

Each example is self-contained, with its own `README.md`, notebook, and sample input file(s) where needed. You can explore a notebook interactively in JupyterLab or execute it from the terminal.

## Notebook examples

| # | Example | What you'll learn | Notebook |
|---|---|---|---|
| 01 | [Basic IP Geolocation Lookup](./01_basic_ip_lookup/README.md) | Look up one IP address and inspect the API response. | [Open](./01_basic_ip_lookup/01_ip2locationio_basic_ip_lookup.ipynb) |
| 02 | [Batch IP Lookup from CSV](./02_csv_batch_lookup/README.md) | Enrich a CSV of IP addresses while avoiding duplicate requests. | [Open](./02_csv_batch_lookup/02_ip2locationio_csv_batch_lookup.ipynb) |
| 03 | [Website Visitor Geolocation](./03_website_visitor_geolocation/README.md) | Analyze Apache/Nginx access logs by visitor geography. | [Open](./03_website_visitor_geolocation/03_ip2locationio_website_visitor_geolocation.ipynb) |
| 04 | [VPN, Proxy, and Tor Detection](./04_vpn_proxy_tor_detection/README.md) | Review available anonymous-network and security signals. | [Open](./04_vpn_proxy_tor_detection/04_ip2locationio_vpn_proxy_tor_detection.ipynb) |
| 05 | [Suspicious Login Detection](./05_suspicious_login_geolocation/README.md) | Investigate country changes and possible impossible travel. | [Open](./05_suspicious_login_geolocation/05_ip2locationio_suspicious_login_geolocation_fixed.ipynb) |
| 06 | [Website Content Localization](./06_website_content_localization/README.md) | Suggest language, currency, and regional content from an IP location. | [Open](./06_website_content_localization/06_ip2locationio_website_content_localization.ipynb) |
| 07 | [Geographic Audience Segmentation](./07_geographic_audience_segmentation/README.md) | Compare website traffic, conversions, and revenue by market. | [Open](./07_geographic_audience_segmentation/07_ip2locationio_geographic_audience_segmentation.ipynb) |
| 08 | [International Campaign Scheduling](./08_international_campaign_scheduling/README.md) | Plan send times across time zones with daylight-saving awareness. | [Open](./08_international_campaign_scheduling/08_ip2locationio_international_campaign_scheduling.ipynb) |
| 09 | [Geofencing and Regional Access Control](./09_geofencing_regional_access_control/README.md) | Evaluate country/region policies with allow, deny, and review results. | [Open](./09_geofencing_regional_access_control/09_ip2locationio_geofencing_regional_access_control.ipynb) |
| 10 | [Network and ISP Intelligence](./10_network_isp_intelligence/README.md) | Analyze ASN, ISP, network types, and traffic distribution. | [Open](./10_network_isp_intelligence/10_ip2locationio_network_isp_intelligence.ipynb) |

## Requirements

- Python **3.9 or newer**
- Internet access for live API lookups
- An [IP2Location.io API key](https://www.ip2location.io/) for authenticated lookups (optional for supported keyless requests)
- JupyterLab and the Python packages used by the examples

## Getting started

**1. Clone the repository:**

```bash
git clone https://github.com/ip2location/ip2location-io-notebook-examples.git
cd ip2location-io-notebook-examples
```

**2. Create and activate a virtual environment (recommended):**

macOS / Linux:

```bash
python3 -m venv .venv
source .venv/bin/activate
```

Windows PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

**3. Install the dependencies:**

```bash
python -m pip install jupyterlab nbconvert ipykernel requests pandas matplotlib tzdata
```

**4. Open an example notebook:**

```bash
cd 01_basic_ip_lookup
python -m jupyter lab 01_ip2locationio_basic_ip_lookup.ipynb
```

To run a notebook **entirely from the terminal**, without starting JupyterLab, use `nbconvert` in the example's directory:

```bash
python -m jupyter nbconvert --to notebook --execute --ExecutePreprocessor.timeout=600 --output executed_01.ipynb 01_ip2locationio_basic_ip_lookup.ipynb
```

The executed copy saves cell outputs. Replace the notebook filename with the example you want to run, and keep its sample input files in the same directory. See each example's `README.md` for its exact command, settings, and output files.

## API key configuration

Set your API key as an environment variable **before** starting JupyterLab or running the notebook:

macOS / Linux:

```bash
export IP2LOCATION_API_KEY="YOUR_API_KEY"
export IP2LOCATION_IO_API_KEY="YOUR_API_KEY"
```

Windows PowerShell:

```powershell
$env:IP2LOCATION_API_KEY="YOUR_API_KEY"
$env:IP2LOCATION_IO_API_KEY="YOUR_API_KEY"
```

Most notebooks read `IP2LOCATION_API_KEY`; **examples 04 and 05** read `IP2LOCATION_IO_API_KEY`. Both variables may contain the same key. Never commit real API keys to GitHub.

## Demo mode and live mode

- **Examples 01–03** make live API requests when executed and require internet access.
- **Examples 04–10** default to `MODE = "demo"`, using explicitly synthetic data without calling the API. To query real IP addresses, change the configuration cell to `MODE = "live"` and rerun the notebook.
- Some API response fields, such as detailed proxy, ISP, or time-zone information, depend on the subscription plan. Notebooks handle missing fields where applicable.
- Live queries may count toward your API usage limits. Review each notebook's maximum lookup setting before processing larger files.

## Data and results

Sample CSV and log files are provided for learning and testing. Many notebooks generate CSV reports, summary tables, or charts; output locations are documented in their individual READMEs. Demo-mode results are **illustrative**, not real IP2Location.io lookups.

**Note:** IP geolocation provides an estimated network location, not a device's GPS position. Security flags, impossible-travel indicators, and geofencing examples are intended as demonstrations and should not be used as the sole basis for high-impact decisions.

## Resources

- [IP2Location.io website](https://www.ip2location.io/)
- [IP2Location.io API documentation](https://www.ip2location.io/ip2location-documentation)
- [IP2Location GitHub organization](https://github.com/ip2location)

Questions or suggestions? Open an [issue](https://github.com/ip2location/ip2location-io-notebook-examples/issues) in this repository.
