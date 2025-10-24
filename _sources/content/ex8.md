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
