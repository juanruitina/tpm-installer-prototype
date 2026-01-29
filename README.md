# TPM Installer Prototype

Prototype UI for exploring hardware-backed encryption availability and actions microcopy driven by CSV data exported from Google Sheets.

## Overview
- UI: `index.html` (simple static page).
- Data: `data/errors.csv` and `data/actions.csv`.

## CSV format
- The app expects comma-separated values (CSV), not TSV. The built-in `parseCSV` function splits headers on commas and treats `"` as a quote toggle.
- Limitations: the parser is simplistic — it does not fully implement RFC4180 (e.g., escaped double-quotes `""` inside fields are not handled robustly). For complex CSVs, prefer producing RFC4180-compliant files or switching to a proper CSV parser.

## Usage
1. Serve the directory and open `index.html` in your browser. Example using Python:

```sh
python3 -m http.server 8000
# then open http://localhost:8000/index.html
```

2. Optional URL query params:
- `?vendor=Dell|Lenovo|HP|Other` — preselects vendor (default: Other).
- `?keepOpen=1` — open all solution details by default.

3. Edit data in `data/errors.csv` and `data/actions.csv`; the UI reads them on load.