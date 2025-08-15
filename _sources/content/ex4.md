# Exercise4: 3D Visualization and 3D Animation
## Warm Up


## Task
In this exercise, you’ll move from **2D mapping** to **3D visualization** in ArcGIS Pro. You will set up and display spatial information in three dimensions, create realistic **3D symbols** for buildings, street furniture, and monuments, capture GNSS points, and finish by producing a **3D animation** and exporting it as a video.

### Overview
- [ ] **Prepare building layer and extrude into 3D**
  - assign heights and visualize buildings in three dimensions.  
- [ ] **Create and manage a Local Scene** 
  - set up a 3D workspace using a local UTM projection for accurate measurements.  
- [ ] **Digitize and symbolize new 3D point features** 
  - add trees, streetlights, benches, and landmarks from imagery.  
- [ ] **Classify and orient features** 
  - use attributes to control rotation, style, and size of symbols.  
- [ ] **Import and position custom 3D models** 
  - replace simple shapes with detailed building/monument models.  
- [ ] **Capture GNSS points and visualize in 3D** 
  - import GPS measurements and align them with the scene.  
- [ ] **Create a fly-through animation** 
  - set camera paths, transparency changes, and annotations.  
- [ ] **Export animation to video** 
  - produce a shareable MP4 file and submit.  

---

## Descriptions & Steps

### Data
  - `Data Students.gdb` (buildings, roads)  
  - `Park-cadastral.tif`  
  - `TUM.dae`  
  - `Old_Pinakothek.dae`  
  - `Monuments.gpx`  
  - `Track.gpx`

### 1. Preparing and Extruding Buildings
- Select buildings with `level_num` = 0 or NULL and assign default value **3**.
- Create a **Local Scene** and add `Buildings` and `Roads`.
- Extrude buildings by `$feature.level_num * 4` (meters per floor).

### 2. Coordinate System & Navigation
- Change scene projection to **ETRS 1989 UTM Zone 32N**.
- Explore 3D navigation tools and mouse controls.

### 3. Digitizing New 3D Features
- Create point feature classes for trees, streetlights, benches, and landmarks with Z-values enabled.
- Digitize features from cadastral plan and aerial imagery.
- Place anchor points for TUM and Old Pinakothek.

### 4. 3D Symbolization
- Apply built-in 3D marker symbols to point layers.
- Classify park benches by `Orient` attribute and adjust rotation.
- Replace extruded landmark buildings with **custom 3D models** and position them correctly.

### 5. Capturing & Displaying GNSS Points
- Use GPS device to record monument locations (20 averaged points each).
- Convert GPX files to shapefiles using GPS Utility.
- Define projection as WGS 1984 and symbolize monuments with custom 3D models.

### 6. Creating a 3D Animation
- Plan keyframes for viewpoints and transitions.
- Adjust transparency, add titles, and set duration.
- Export animation as MP4 (YouTube preset) and submit.

---

## Optional Task
- Write a script to update building heights from a CSV file.
- Automate GPX-to-shapefile conversion using `ogr2ogr`.


---

## Materials
- [Scenes in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/mapping/scenes/what-is-a-scene-.htm)  
- [Extrude features to 3D](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/extrude-features-to-3d.htm)  
- [3D symbols and styles](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/3d-symbols.htm)  
- [Import 3D models](https://pro.arcgis.com/en/pro-app/latest/help/mapping/layer-properties/import-3d-models.htm)  
- [GPS Utility](http://www.gpsu.co.uk/)  
- [Animation in ArcGIS Pro](https://pro.arcgis.com/en/pro-app/latest/help/mapping/animation/overview-of-animation.htm)


