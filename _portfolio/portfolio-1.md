---
title: "Habitat Suitability Analysis for Puma concolor coryi"
excerpt: "Click the link above for more details <br/><img src='/images/suitability.png' width='395'>"
collection: portfolio
---

This project uses GIS-based multi-criteria analysis to identify suitable habitat for the endangered Florida panther (Puma concolor coryi). Environmental and anthropogenic factors including land cover, vegetation health, roadway proximity, and storm surge risk were reclassified and weighted to produce a composite habitat suitability surface. The resulting model highlights priority areas for conservation, restoration, and potential habitat expansion.

---

## Workflow

### 1: Data Inputs
* Land cover
* Vegetation Condition Index (VCI)
* Distance to roads
  * Euclidean Distance was used to calculate distance from roadways, as panthers are highly sensitive to road presence
* Storm surge

These variables represent key ecological and anthropogenic drivers of habitat suitability for Florida panthers

### 2: Reclassification 
Each variable was reclassified into a standardized 1–5 suitability scale based on ecological relevance

<table class="suitability-table">
  <thead>
    <tr>
      <th>Factors</th>
      <th>5<br>Highly Suitable</th>
      <th>4<br>Suitable</th>
      <th>3<br>Moderately Suitable</th>
      <th>2<br>Marginally Suitable</th>
      <th>1<br>Not Suitable</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Land Cover</td>
      <td>Natural Forests</td>
      <td>Wetlands</td>
      <td>Emergent Wetlands</td>
      <td>Agriculture</td>
      <td>Urban / Developed</td>
    </tr>
    <tr>
      <td>VCI</td>
      <td>&gt; 0.85</td>
      <td>0.70–0.85</td>
      <td>0.5–0.7</td>
      <td>0.35–0.50</td>
      <td>&lt; 0.35</td>
    </tr>
    <tr>
      <td>Distance to Roadways (meters)</td>
      <td>&gt; 5,000</td>
      <td>2,500–5,000</td>
      <td>1,000–2,500</td>
      <td>500–1,000</td>
      <td>&lt; 500</td>
    </tr>
    <tr>
      <td>Storm Surge</td>
      <td>No Flooding / Cat 5</td>
      <td>Cat 4</td>
      <td>Cat 3</td>
      <td>Cat 2</td>
      <td>Cat 1</td>
    </tr>
  </tbody>
</table>

### 3: Create Transformed Maps for Suitability Modeler 

<img 
    src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/landcover.png"
    alt="Transformed Land"
    width="400"
    style="height: auto;">

Figure 1. Reclassified land cover suitability surface
Higher values indicate preferred habitat types such as forest and wetlands.

<img 
    src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/roads.png"
    alt="Transformed Land"
    width="400"
    style="height: auto;">

Figure 2. Reclassified Distance to Roadways Suitability Surface
Higher values indicate areas farther from major roadways, which are more suitable for Florida panthers due to reduced human disturbance and lower risk of vehicle collisions.

<img 
    src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/stormsurge.png"
    alt="Transformed Land"
    width="400"
    style="height: auto;">

Figure 3. Reclassified Storm Surge Risk Suitability Surface
Higher suitability values correspond to areas less vulnerable to coastal flooding, reflecting the preference for stable habitats not subject to frequent storm inundation.

<img 
    src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/vegetation.png"
    alt="Transformed Land"
    width="400"
    style="height: auto;">

Figure 4. Reclassified VCI Suitability Surface
Higher values represent areas with healthier and denser vegetation, which provide better cover and prey availability for Florida panthers.

### 4: Weighted Overlay 
A weighted overlay approach was used to combine factors, with land cover and road proximity receiving the greatest weight due to their importance in panther habitat selection.

1. Land Cover- 35%
1. Distance to Roadways- 30%
1. Vegetation Condition- 20%
1. Storm Surge Risk- 15%

## Final Suitability Model
The resulting raster identifies areas of high and low suitability, highlighting potential zones for conservation and expansion

<img 
    src="https://raw.githubusercontent.com/LeannaNavo/leannanavo.github.io/refs/heads/master/images/suitability.png"
    alt="Transformed Land"
    width="400"
    style="height: auto;">

The habitat suitability model indicates that the most suitable habitat for the Florida panther is concentrated in South Florida, particularly around the Everglades and Big Cypress regions. Much of the rest of the state shows moderate to low suitability, with coastal and urbanized areas being especially unsuitable due to development and habitat fragmentation. The fragmented pattern of suitable habitat highlights the importance of protecting core habitats and maintaining wildlife corridors to support panther movement and population expansion.

---

### Tools

* Euclidean Distance
* Clip Raster
* Reclassify Raster
* Suitability Modeler
* Raster Calculator
* Polygon to Raster Calculator

***

### Data Sources:
* Florida Department of Transportation
* USDA Farm Services Agency
* National Land Cover Database
* NOAA Hurricane Center


