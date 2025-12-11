# Land Cover Classification from Sentinel-2 Imagery

## Overview
This tutorial demonstrates land cover classification using Sentinel-2 satellite imagery and spectral indices. The workflow classifies pixels into five main categories: Water, Bare Soil, Urban, Field, and Forest using a rule-based approach.

## Key Features
- **Multi-Index Analysis**: Combines NDVI (vegetation), MNDWI (water), BSI/BI (bare soil), NUAI/NDBI (urban), and CHM (canopy height)
- **Hierarchical Classification**: Sequential rule-based algorithm with priority-based logic (Water → Bare Soil → Urban → Vegetation)
- **IGN Data Integration**: Incorporates French IGN elevation models (DSM/DTM) to compute Canopy Height Model (CHM)

## Classification Logic
1. **Water**: Detected first using MNDWI > 0
2. **Bare Soil**: Two detection paths - BSI-based (agricultural) or BI-based (bright surfaces)
3. **Urban**: Spectral indices (NUAI, NDBI) excluding bare soil areas
4. **Field/Forest Split**: CHM threshold (2.5m) separates low vegetation (fields) from tall vegetation (forests)
5. **NDVI Refinement**: Final thresholds ensure accurate vegetation classification
