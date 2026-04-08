# Suriname Cruise Services Catalogue

Official directory of cruise service providers for Paramaribo, Suriname.
Published by **SITA — Suriname Investment & Trade Agency**.

Live site: https://mottumdata.github.io/SITA_Cruises_Services/

---

## Updating provider data with a new CSV export

The catalogue data comes from HubSpot CRM exports. When new providers register or existing entries are updated, follow these steps.

### 1. Export from HubSpot

In HubSpot, go to **Contacts → Companies**, filter by the Cruise Services view, and export as CSV. Name the file with today's date, e.g.:

```
hubspot-crm-exports-cruises-services-companies-2026-05-01.csv
```

### 2. Add the CSV to the `data/` folder

Place the new file in `data/`. Keep the old files — the workflow always picks the newest one by modification date.

### 3. Push to GitHub

```bash
git add data/<your-new-file>.csv
git commit -m "data: add CRM export YYYY-MM-DD"
git push
```

### 4. What happens automatically

The GitHub Actions workflow (`.github/workflows/update-catalogue.yml`) triggers on any push to `data/*.csv`. It:

1. Detects the newest CSV in `data/` by modification time.
2. Copies it to `data/latest.csv`.
3. Commits and pushes `data/latest.csv` back to the repo.

You can monitor the run under **Actions** in the GitHub repository.

---

## Adding a new provider to the catalogue

The JavaScript `DATA` array in `index.html` must be updated manually after a new provider is confirmed. Each entry maps directly to the fields in the SITA registration form.

1. Open `index.html` and find the `DATA` array (around line 330).
2. Copy an existing entry as a template and fill in the new provider's fields.
3. If the provider has a logo, add the image to `Visuals/` and register it in `data/logos.json`:
   ```json
   { "logos": { "<KKF_NUMBER>": "Visuals/<filename>.png" } }
   ```
4. Commit and push — GitHub Pages deploys automatically.

---

## Repository structure

```
index.html          — Single-page application (all HTML, CSS, JS)
data/               — HubSpot CSV exports + logos.json
Visuals/            — Provider logos and SITA brand assets
Context/            — Project knowledge base and form reference
.github/workflows/  — CI: auto-update data/latest.csv on CSV push
DESIGN.md           — Design system specification
```

---

## Contact

SITA — Suriname Investment & Trade Agency  
Brokopondolaan 97, Paramaribo, Suriname  
info@sita.sr · peu-management@sita.sr
