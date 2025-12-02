# E8: Spatial Data Integration
## Warm Up
### Spatial data is more than the map
When we think of spatial data, we often imagine maps or satellite imagery.  
But in reality, **spatial information is embedded in many unexpected places** — and integrating them is a key part of modern spatial analysis.

Here are some surprising yet common carriers of geographic data:
```{admonition} Where is Spatial Data Hiding?
:class: note
- **Social Media**:  
  Platforms like Twitter, Instagram, or TikTok often contain **geotagged posts**, hashtags, or place names. We can extract location, timestamp, sentiment, and even movement patterns from such content.
- **Images & Videos**:  
  Think about [GeoGuessr](https://www.geoguessr.com/), Google Street View, or drone footage. Even a single image can contain clues:  
    - GPS coordinates in metadata  
    - Landmarks for visual recognition  
    - Scene type (urban/rural/coastal?) via machine learning
> That’s right — there’s even a competition to see who can guess the location the fastest just from an image.
The amount of geographic information hidden in a photo is far beyond what you’d expect. 👉 Watch the [video](https://www.youtube.com/watch?v=9Wbau6wdKzI).
- **Statistical Data**:  
  Spreadsheets with **addresses, zip codes, or coordinates** are everywhere — surveys, business data, even class attendance logs. With geocoding(like [Geocoding API](https://developers.google.com/maps/documentation/geocoding/overview)), you can convert them into mappable features.

```
 🎯 Why This Matters  
Spatial analysis today is about finding location **within messy, real-world data**, and bringing everything together to answer complex questions.

### Space Time Cube
The **Space-Time Cube (STC)** is a powerful way to visualize and analyze events that unfold across both **space** and **time**. Imagine stacking maps on top of each other — one map per time step. Each cube represents **a location + a time interval**, allowing us to track patterns like:

- **Emerging hotspots**  
- **Coldspots fading away**  
- **Recurrent activity patterns**  
- **Sudden spikes (e.g., in crime, traffic, or tweets)**
```{figure} ../images/ex8/SBC01.png
---
name: Stc-fig
---
Space Time Cube
```
> Space-Time Cubes are especially useful for dynamic data like population movement, traffic flow, or disease spread.

## Task
### Data
- {download}`Geolife_user_153.csv <../data/E8/153_stay.csv>`
- {download}`Geolife_multipleusers.csv <../data/E8/users_66_150_stay_points.csv>`
- {download}`Beijing_road <../data/E8/北京路网.rar>`
- {download}`Weibo_check_in_data <../data/E8/BeijingCheckInRecordsfromSinaWeibo.zip>`
- {download}`affine.csv <../data/E8/affine.csv>`

### Advanced Task

#### Extracting Stationary and Moving Points from GPS Data
Work with full-scale GPS trajectory data to distinguish between stationary points (e.g., home, workplace) and moving points (e.g., travel, commute). You can take our code as a [reference](https://github.com/FullToker/geo-information_ex08).
**Steps:**
- Download the entire GPS dataset (Geolife full trajectories).
- Use clustering or stay-point detection methods to identify relatively fixed points.
- Map these points over the city road network & Analyze distribution patterns.

#### Extracting Location Info from Raw Social Media Data
Work with original social media datasets (JSON or CSV format) to parse and georeference geographic information. You can look for datasets from [awesome-twitter-data](https://github.com/shaypal5/awesome-twitter-data) or other sources.

**Steps:**
- Extract place names, coordinates, or geo-tags.
- Perform **geocoding** if only place names are given.
- Integrate results into your base map (e.g., city districts, roads).
- Evaluate accuracy and coverage.

#### Merging and Comparing Road Network Data
Work with different road network datasets (e.g., official shapefiles and OSM data) to merge, simplify or validate topology.

**Steps:**
- Merge multiple segments into unified roads where possible.
- Compare with OpenStreetMap (OSM) data:
  - Are all roads captured?
  - Are there mismatches or topological errors?
- Use topology tools to **check overlaps, gaps, or pseudo nodes**.



### Reference
This exercise is primarily based on the works:

- Huang, W. et al. (2015). *Predicting human mobility with activity changes*. **International Journal of Geographical Information Science**, 29(9), 1569–1587. https://doi.org/10.1080/13658816.2015.1033421
- Long Y, Liu X, 2013, *How mixed is Beijing, China? A visual exploration of mixed land use* Environment and Planning A 45: 2797–2798


## Materials
- [Geospatial Data Integration, by Thierry Warin](https://warin.ca/geospatial/12-data_integration.html)
- [Overview of georeferencing, by ESRI ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/data/imagery/overview-of-georeferencing.htm)
- [Georeferencing, Wiki](https://en.wikipedia.org/wiki/Georeferencing)
- [Unlocking the Power of Spatial Data Integration, by ESRI](https://mediaspace.esri.com/media/Regional%20and%20Cross-Jurisdictional%20Collaboration%3A%20Unlocking%20the%20Power%20of%20Spatial%20Data%20Integration/1_i39tp96v)

