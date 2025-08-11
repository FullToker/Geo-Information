# Exercise4: 3D Visualization and 3D Animation
## Warm Up


## Task
### Overview
You will:
- [ ] Prepare and extrude building footprints into 3D using height attributes.
- [ ] Create a **Local Scene** in ArcGIS Pro and set the correct projected CRS.
- [ ] Create and digitize new 3D features (trees, benches, streetlights, anchor points).
- [ ] Symbolize features with **built-in** and **custom 3D models**.
- [ ] Capture and import GNSS points of monuments, then display them in 3D.
- [ ] Create a **3D animation** (keyframes, transparency, text overlay) and export as a video.

---

## Descriptions

### 1. Prepare Buildings and Extrude
- Select buildings with `level_num` = 0 or NULL → set to 3.
- Insert a **New Local Scene**, add buildings and roads.
- Use **Extrusion** with Arcade expression `$feature.level_num * 4` (4 m per level).

### 2. Set Scene CRS
- Change to **ETRS 1989 UTM Zone 32N** for better local accuracy.

### 3. Create 3D Feature Classes
- In the geodatabase, create Z-enabled feature classes:  
  `Trees` (points), `StreetLights` (points), `ParkBenches` (points), `OldPinakothek` (point), `TUM` (point).

### 4. Digitize New Features
- Add park cadastral plan and digitize trees, benches, and lamps.
- Add anchor points for Old Pinakothek and TUM.

### 5. Symbolize with 3D Models
- For `Trees`, `StreetLights`, `ParkBenches` → assign built-in 3D symbols.
- For benches:  
  - Add `Orient` field, categorize benches by orientation.
  - Rotate models according to category.
- Import custom `.dae` models for TUM and Old Pinakothek.

### 6. GNSS Monuments
- Capture points with GPS, export `.gpx`, convert to shapefiles.
- Define projection as WGS 1984.
- Symbolize monuments by type using custom 3D models and real-world units.

### 7. 3D Animation
- Create animation keyframes by navigating through viewpoints.
- Add transparency changes and text overlays.
- Export video (e.g., YouTube preset, MP4 format) and upload.

---

## Optional Task (Programming Focus)
- **3D extrusion from attributes**  
  Load building footprints (Shapefile/GeoPackage), extrude in a 3D library (e.g., `pyvista`, `vtk`) based on height attributes.
- **Custom symbol placement**  
  Read point features (trees, benches) and place corresponding 3D models programmatically.
- **GNSS data processing**  
  Parse GPX files in Python (`gpxpy`), transform to a projected CRS, and export as shapefiles.
- **Simple 3D animation**  
  Create a camera path around the scene using Python (e.g., `pyvista.Plotter`), export as MP4.

---

## Materials
- ArcGIS Pro Documentation:  
  - [Scenes in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/mapping/scenes/what-is-a-scene.htm)  
  - [Extrusion in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/extrude-features.htm)  
  - [3D Symbology](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/3d-symbology.htm)  
  - [Animation in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/mapping/animation/overview-of-animation.htm)  
- TUM Moodle files:  
  - `Data Students.gdb` (buildings, roads)  
  - `Park-cadastral.tif`  
  - `TUM.dae`  
  - `Old_Pinakothek.dae`  
  - `Monuments.gpx`  
  - `Track.gpx`

