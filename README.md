# Land Cover Classification from Sentinel-2 Imagery

## 📓 Viewing the Notebook

⚠️ **Note:** This notebook is too large to be displayed directly on GitHub due to its size and embedded visualizations.

**Please use NBViewer to view the complete notebook:**  
👉 **[Open in NBViewer](https://nbviewer.org/github/stevo32800/land_cover_classification_part2/blob/main/classify_pixel_part2.ipynb)**

### Alternative Options:
- Clone the repository and run it locally

## 👁️ Overview
This tutorial demonstrates land cover classification using Sentinel-2 satellite imagery and spectral indices. The workflow classifies pixels into five main categories: Water, Bare Soil, Urban, Field, and Forest using a rule-based approach.

## ⭐ Key Features
- **Multi-Index Analysis**: Combines NDVI (vegetation), MNDWI (water), BSI/BI (bare soil), NUAI/NDBI (urban), and CHM (canopy height)
- **Hierarchical Classification**: Sequential rule-based algorithm with priority-based logic (Water → Bare Soil → Urban → Field → Forest)
- **IGN Data Integration**: Incorporates French IGN elevation models (DSM/DTM) to compute Canopy Height Model (CHM)

## 🤖 Classification Logic
1. **Water first**: most distinctive with MNDWI
2. **Bare Soil**: Before urban (similar spectral signatures)
3. **Urban**: After bare soil, using NUAI range + NDBI + BI
4. **Field third**: Medium NDVI + medium/low height
5. **Forest**: High NDVI + tall height


