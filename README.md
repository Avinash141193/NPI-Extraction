# NPI Registry Lookup Tool

A web app to look up provider information from the CMS NPPES NPI Registry.

## Features
- Single NPI lookup with full details displayed on screen
- Batch upload Excel file → auto-fetches all NPIs → download enriched file
- All 13 fields captured: NPI, Enumeration Date, NPI Type, Status, Provider Name,
  Authorized Official, Mailing Address, Primary Practice Address,
  Secondary Practice Address, Health Information Exchange,
  Other Identifiers, Taxonomy

## Project Structure
```
npi-app/
├── app.py              ← Flask backend
├── requirements.txt    ← Python dependencies
├── render.yaml         ← Render.com deploy config
└── templates/
    └── index.html      ← Frontend UI
```

## Deploy to Render.com

### Step 1 — Push to GitHub
1. Create a new GitHub repository (e.g. `npi-lookup`)
2. Upload all files from this folder into that repo

### Step 2 — Connect to Render
1. Go to https://render.com and sign in
2. Click **New → Web Service**
3. Connect your GitHub repo
4. Render will auto-detect the `render.yaml` config

### Step 3 — Deploy Settings (if not using render.yaml)
- **Runtime**: Python 3
- **Build Command**: `pip install -r requirements.txt`
- **Start Command**: `gunicorn app:app`
- **Instance Type**: Free

### Step 4 — Done!
Render gives you a live URL like: `https://npi-registry-lookup.onrender.com`

## Run Locally (for testing)
```bash
pip install -r requirements.txt
python app.py
# Open http://localhost:5000
```
