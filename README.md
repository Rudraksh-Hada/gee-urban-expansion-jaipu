# Urban Expansion & Vegetation Loss – Jaipur (2014–2024)

Google Earth Engine project to analyze how urban growth in Jaipur has impacted vegetation between 2014 and 2024.

## Overview

- Platform: Google Earth Engine (Code Editor)
- Data: Landsat 8 Surface Reflectance (Collection 2, Tier 1)
- Location: Jaipur, Rajasthan, India (rectangular ROI around city core)
- Indices:
  - NDVI – Normalized Difference Vegetation Index
  - NDBI – Normalized Difference Built‑up Index

## What the Script Does

- Loads Landsat 8 SR imagery for 2014–2024
- Masks clouds using the QA_PIXEL band
- Computes:
  - NDVI_2014 and NDVI_2024
  - NDBI_2014 and NDBI_2024
- Creates change layers:
  - NDVI_change = NDVI_2024 − NDVI_2014
  - NDBI_change = NDBI_2024 − NDBI_2014
- Classifies:
  - Vegetation loss (NDVI_change < threshold)
  - New urban area (NDBI_change > threshold)
- Computes area statistics for the ROI in km²
- Builds an NDVI time‑series chart (2014–2024)

## Outputs

- NDVI Change Map  
  - Red = vegetation loss  
  - Green = vegetation gain  

- NDBI Change Map  
  - Red = urban expansion  

- NDVI Time‑Series Chart  
  - Mean NDVI per year over the ROI

- Area Statistics (example format)  
  - Vegetation loss: X.xx km²  
  - New urban area: Y.yy km²  

(Values depend on ROI, thresholds and final run.)

## Files

- `jaipur_ndvi_ndbi.js` – Earth Engine script with:
  - Data loading and cloud masking
  - NDVI/NDBI computation (2014 & 2024)
  - Change detection
  - Area statistics
  - NDVI time‑series chart

- `screenshots/` (optional)
  - `ndvi_change_map.png`
  - `ndbi_change_map.png`
  - `console_stats.png`

## How to Run

1. Open https://code.earthengine.google.com  
2. Create a new script and paste `jaipur_ndvi_ndbi.js`  
3. Adjust ROI if needed  
4. Click **Run**  
5. Use the Layers panel to view:
   - NDVI Change
   - NDBI Change  
6. Read km² values and NDVI chart from the Console

## Skills Demonstrated

- Remote sensing with Landsat 8
- NDVI / NDBI computation
- Change detection and basic time‑series analysis in GEE
- Quantifying environmental impact of urban expansion
