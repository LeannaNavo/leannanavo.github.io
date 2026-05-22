---
title: "hermal Stress and Habitat Vulnerability of Coral Reefs in the Florida Keys"
excerpt: "Click the link above for more details <br/><img src='/images/coralthreatened.gif' width='395'>"
collection: portfolio
---

This project uses GIS and remote sensing data to assess how elevated sea surface temperatures (SST) contribute to coral reef stress in the Florida Keys. By combining coral habitat data with temperature thresholds associated with bleaching events, this analysis identifies spatial patterns of coral vulnerability across multiple years to answer the question: How have rising global sea surface temperatures in 2016, 2018, 2020, 2022, and 2024 been associated with thermal stress in Florida Keys coral reef systems? .

## Workflow

### 1. Defining the Study Area
* Extracted the Florida Keys Marine Sanctuary (FKMS) boundary using the Eliminate Polygon Part Tool
* Ensured analysis was restricted to ecologically relevant marine areas

### 2. Mapping Coral Habitat
* Used Select by Attributes to isolate coral reef and hardbottom habitats (excluded seagrass, sediment, and patch reef features)
* Clipped coral data to the FKMS boundary
* Converted vector coral polygons to raster using Polygon to Raster
   * Assigned value = 1 to represent coral presence

### 3. Processing Temperature Data
* Imported SST data from NetCDF (.nc) files using Make Multidimensional Raster Layer
* Extracted summer months using Aggregate Multidimensional Raster
* Clipped global SST data to the Florida Keys study area
* Reclassified SST values:
  * ≥ 30°C → 1 (thermal stress threshold)
  * < 30°C → 0 (non-stress conditions)

### 4. Aligning Spatial Data
* Use Resample to ensure consistent spatial resolution between coral and temperature rasters

### 5. Identifying Threatened Coral
* Used Raster Calculator: Threatened Coral = Coral Presence × Temperature Stress
* Only pixels representing both coral presence and high temperature remain, represented thermally stressed coral 





## Final Output (Gif) 

<figure>
  <img src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/coralthreatened.gif" alt="Threatened coral">
  <figcaption> Note: Unnaturally straight lines are due to data limitations, reflecting SST raster resolution of 0.25°</figcaption>
</figure>

## Quantified Yearly Threats to Coral Health

| Year | Percent of Coral Threatened |
|------|-----------------------------|
| 2016 | 22.8                        |
| 2018 | 10.7                        |
| 2020 | 23.0                        |
| 2022 | 23.0                        |
| 2024 | 85.7                        |

Thermal stress varies significantly across years, with 2024 showing a dramatic increase in coral exposure to high temperatures. The results suggest that recent warming trends may be intensifying coral vulnerability at a rapid pace

---

### Tools

* Eliminate Polygon Part Tool
* Select by Attributes
* Clip
* Polygon to Raster
* Make Multidimensional Raster Layer
* Aggregate Multidimensional Raster
* Reclassify
* Resample
* Raster Calculator
* Gif Animator

***

### Data Sources:
* NOAA
* Florida Fish and Wildlife Conservation Commission
