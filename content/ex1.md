# Exercise1: Selecting and Editinfg Features

## Warm Up
Firstly, let’s take a moment to talk about a very important (and maybe slightly mysterious) word:
👉 Feature.

### What Does "Feature" Mean in Data Science?
In data science and machine learning, a feature is just a fancy word for: A column in your table that describes something about your data.

For example, if you're building a model to predict house prices, features might include:
  - Number of bedrooms 🛏️
  - Square footage 📐
  - Distance to the nearest train station 🚉
  - Year built 

These features feed into your models, visualizations, and decisions. This process — turning messy, real-world data into usable, structured information — is called data engineering(machine learning engineer also covers this).🛠️Typical Workflow of DS or MLE is like: 
> Data collection -> Raw data → Preprocessing → Feature extraction → Model / Analysis

```{admonition} Features of Special Format
In other fields, “features” can look very different:
- 🖼️ In **computer vision**:  
  Each pixel can be considered a feature — or features might be higher-level elements like **color patterns**, **shapes**, or **edges**.
- 🧠 In **NLP (Natural Language Processing)**:  
  Features could include **word counts**, **sentence length**, or **embeddings** from a language model.  
  > For example, in [Transformers](https://arxiv.org/abs/1706.03762), each token is represented as a **512-dimensional vector**.
- 🧊 In **3D data**:  
  Features might be **points in a point cloud**, **meshes**, or **implicit surfaces** — used in fields like LiDAR, AR/VR, or 3D modeling & generation.
- 🎥 In **4D data** (e.g., video):  
  Each **frame** can be treated as a feature, and you might also extract features **within** a frame (like objects), or track features **across time** (motion, trajectory, etc.).
- 🗺️ In **spatial data** (our focus today!):  
  A feature is a **real-world geographic object** — something that has both **location** and **descriptive attributes**.  
  > Think of roads, buildings, rivers, or tram stops — all stored with geometry and fields in shapefiles or geodatabases.

And just like in other fields, we still care about their properties — but now they’re stored in attribute tables.
```
> Take it easy — imagine you're the computer. For every item in a dataset, the things you store or know about it are called features.
Features can be:
- Built-in (directly collected from raw data)
- Extracted, filtered, or converted from original information (e.g., converting time to day of week, [PCA](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.PCA.html))
- Learned through machine learning or deep learning models — though these learned features can sometimes be a bit mysterious 🤖✨

---

### What Are Feature and what are Fields in a Shapefile?
In this exercise, a **feature** specifically refers to a **geometry object** — such as a point, line, or polygon — representing a real-world location. Each feature typically consists of two parts:
- **Geometry**:
Describes where it is, including spatial shape and location.
Also includes auxiliary information like the Coordinate Reference System (CRS).
- **Attribute Fields**:
Describe what it is — these are the additional properties or metadata stored in a table (e.g., name, type, status, ID, etc.).
> If you read or import shapefiles (or other spatial formats) in your program, you’ll notice that **all the information** — including geometry-related data — is stored as attributes. So in a way, everything becomes a **feature describing the data** — whether it’s where something is (geometry) or what it is (attributes). From the program’s perspective, it’s just a structured collection of information.
```{admonition} ⚠️  Reminders
Always check the **CRS (coordinate reference system)** when working with multiple layers or datasets — mismatched CRS is a common source of confusion!
```

### What makes geoinformation special?

In the lecture, we mentioned three key points that make geospatial data different from other types of data:
1. **Spatial and Temporal Dependence**
Example: Traffic congestion in one district affects neighboring areas; deforestation in one region impacts climate patterns elsewhere.

2. **Spatial Heterogeneity** Example: Rainfall patterns or land use can differ dramatically from one region to another.

3. **Place-Sensitive User Interest** Example: Local air quality reports are much more relevant to nearby residents.

```{admonition} 🔬 Dive more
- In probability theory(e.g. Bayesian Estimation), the assumption of _I.I.D._ (Independent and Identically Distributed) is fundamental.  
  But due to **spatial and temporal dependence**, this assumption often fails in geospatial contexts.  
  👉 How can we address this? → Use models that **account for spatial autocorrelation** rather than assuming independence.

- We can only collect samples at specific locations — e.g., we have **limited and static observations** about weather conditions.  
  👉 How can we estimate values in unsampled areas? → Use **spatial interpolation** techniques such as Kriging or IDW.

- How can we **quantify spatial heterogeneity**?  
  👉 Use **variograms**, **local statistics** (e.g., Local Moran's I), or model non-stationarity with techniques like **GWR (Geographically Weighted Regression)**.
```
> In today’s exercise, you’ll get hands-on experience with how to interact with these features and fields — the fundamental building blocks of geospatial data.

---

## Task
### Overview

- [ ] **Create a new project**, import the provided dataset as a layer, and add a **base map or image layer** to your map view. 
    - Connect a floder to your project
    - Add a database and then add the _buildings_ and _roads_ to the map
    - Add the .tiff file to your map as a layer
- [ ] **Learn how to select features** using different methods:  
  - Select by click 
  - Select by location  
  - Select by attributes  
- [ ] **Process attribute fields**:  
  - Rename fields  
  - Convert field formats (e.g., from string to number)  
- [ ] **Create a new feature class** named _Lawn_ for your own data.  
- [ ] **Edit new features**:  
  - Add now the new Feature Class Lawn to the Map according to the orthophoto
  - Add features such as **tram stops** and **underground stations**  
  - Create a **new feature template** 
- [ ] **Edit attribute data**:  
  - Add new fields  
  - Edit existing values  
  - Calculate field values  
  - Combine editing techniques for efficient workflows  


### Descriptions
Detailed instructions in {download}`Lesson 0 <../doc/Lesson 1.docx>`

#### Data
- `Data Students.gdb`
- `orthophoto.tif`

### Optional Task
- Explore: ESRI Shapefile, TIFF.
- Write a program that loads a shapefile, and try to complete the following tasks:
  - Display the **shape** (rows and columns) and print an **overview** of the data (e.g., first 5 rows or metadata).
  - Create a **new geometry feature** manually (e.g., add a point or a polygon).
  - Process the **attribute fields**, including:
    - Rename a field
    - Filter features based on specific conditions
    - Add a new field and calculate its value
    - Perform a **CRS (Coordinate Reference System) transformation** to reproject the data
  - Return features that match a specific rule or condition, such as:
    - All areas larger than a threshold
    - All points within a bounding box
    - All features of a certain type or category
- If using raster data: perform a basic raster operation, such as clipping, masking, or resampling.

```{admonition} 🔬 Coding Hints
- For **Python**: we suggest using `GeoPandas`, `Shapely`, `Rasterio` (for TIFF), and `Pyproj`.
- For **C++ or C#**: use `GDAL` or `OGR` for both vector and raster data handling.
```

---

## Materials
- [What is a Feature in Machine Learning and Data Science?(by Domino)](https://domino.ai/data-science-dictionary/feature)
- [Introduction to GeoPandas](https://geopandas.org/en/stable/getting_started/introduction.html)
- [What is a shapefile?](https://desktop.arcgis.com/en/arcmap/latest/manage-data/shapefiles/what-is-a-shapefile.htm)
- [What is a Shapefile? by AMDGS](https://www.youtube.com/watch?v=PfbjoAcQp8I&ab_channel=AMDGS)
- [Edit Features Using Editor Tools in ArcGIS Pro | Beginners Guide](https://www.youtube.com/watch?v=i-HDJaZw6dU&ab_channel=TerraSpatial)
- [Editing the Attribute Table in ArcGIS Pro](https://www.youtube.com/watch?v=RnTOzvEpTSU&ab_channel=GeospatialInformationScience)
- [GTiff -- GeoTIFF File Format](https://gdal.org/en/stable/drivers/raster/gtiff.html)
- [ESRI Shapefile / DBF, GDAL](https://gdal.org/en/stable/drivers/vector/shapefile.html)