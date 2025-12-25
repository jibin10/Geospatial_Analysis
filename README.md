# Finding locations to open a gym in Brooklyn, NY

This project uses geospatial analysis + clustering to recommend **potential new gym locations in Brooklyn** that are **close to the Brooklyn city center** and **far from existing gyms/fitness centers**.

#### Full report is included in this repo: **`Report-Finding-locations-to-open-a-gym-in-Brooklyn.pdf`**

## Goal (Constraints)
- Search area: **within 5 km** of Brooklyn city center  
- Competition constraint: candidate locations must be **≥ 2.5 km away** from an existing **Gym/Fitness Center** (and similar venues like boxing clubs/gym pools)

## What it does
- Loads Brooklyn neighborhood coordinates (NYU GeoJSON dataset)
- Uses **Foursquare Places API** to find existing gym/fitness venues
- Generates a dense grid of candidate points (**~200 m spacing**) around the city center
- Filters candidates that satisfy the distance constraints
- Applies **K-Means clustering** to group candidates into “zones”
- Outputs **10 zone centers** as recommended location anchors (optionally reverse-geocoded to addresses)

## Tech Stack
Python, pandas, numpy, scikit-learn, folium, requests  
(Optional) pyproj/geopy for coordinate + distance utilities

## Repo contents
- `Report-Finding-locations-to-open-a-gym-in-Brooklyn.pdf` – full write-up
- `notebooks/` – analysis notebook (if included)
- `src/` – helper modules/scripts (if included)
- `outputs/` – maps / tables (if included)

## Running (typical)
1. Install dependencies
   
   pip install -r requirements.txt

2. Add API keys (example)

#### .env
- FOURSQUARE_API_KEY=your_key_here
- GOOGLE_MAPS_API_KEY=your_key_here   # only if reverse geocoding is used

3. Run the notebook

