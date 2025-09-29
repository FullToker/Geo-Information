# E0: Introduction

## Warm Up

### Some Facts
> Learning the tools and algorithms is only step one. The real goal is using them to solve real-world problems.


In GIS, understanding how things work is important — but knowing why and where to use them is just as essential. Imagine you’re…
- Planning a city-wide cycling event and want to find the safest, greenest, and flattest route for thousands of riders.
- Watching satellite images to see how a newly-built park in your neighborhood slowly turns from brown to vibrant green over a few months.
- Building a map for your favorite hiking trails, letting friends leave geotagged comments and uploading their photos right onto the path.
- Tracking population movement across city districts to help urban planners decide where to build new schools, hospitals, or public transport lines.
- Analyzing anonymized mobile phone data to understand how people move through the city during a big festival, then optimizing bus schedules to handle the crowds.

Based on our experience, there are various ways to implement above tasks:
- Use commerical and powerful(expensive at the same time) software like [ArcGIS Pro](https://www.esri.com/en-us/arcgis/products/arcgis-pro/overview).
- Write lightweight Python scripts using geo-libraries such as [ArcPy](https://pro.arcgis.com/en/pro-app/arcpy/main/arcpy-a-python-package.htm), [Shapely](https://shapely.readthedocs.io/), [GeoPandas](https://geopandas.org/).
- Develop custom applications using pro SDK, like [ArcGIS Engine](https://desktop.arcgis.com/en/arcobjects/latest/net/webframe.htm), [ArcGIS Pro SDK](https://pro.arcgis.com/en/pro-app/latest/sdk/).
- Build standalone desktop applications based on open-source library such as [GDAL](https://gdal.org/en/stable/) and [QT](https://www.qt.io/).
- Create interactive web applications using map services (e.g.[OpenLayers](https://openlayers.org/)) and APIs(e.g. [Google Map API](https://developers.google.com/maps)).
- Use budget-friendly, open-source software such as [QGIS](https://qgis.org/).

You're free to pick your favourite but it's always a bit challenging for rookies to select their hero at the start of the game. 
Here, we've chosen ArcGIS Pro as our main tool. You might be wondering: How did we make that decision? Go ahead, take a guess...

```{admonition} ❓ Why ArcGIS Pro
- [ ] 🎯We spun the wheel and landed on it.
- [ ] 🏛️TUM has already paid the license for us(<del>Most important</del>).
- [ ] It looks pretty fancy(To be honest, vibe coding is much cooler🧑‍💻).
- [ ] It’s fairly easy to get started(Only for Windows users - 😅Sorry Linux & Mac user).
- [ ] It's powerful and comprehensive(Though to be fair, most GIS software claim that).
- [ ] It's backed by Esri — a GIS giant(Esri’s founder, Jack Dangermond, basically invented modern GIS.)
- [ ] It's the tool used in many government agencies and engineering firms(ArcGIS Pro might not be CEO's first love. Those license fees can sting).
```

---

### Exercise Structure
Normally, there will be two documents published of each exercise, 
1. This one — the overview, outlining what you need to do.
2. Another one — a much more detailed, step-by-step guide to help you implement the tasks.

You should start by reading this overview, and refer to the detailed guide if you get stuck or need clarification.

>It’s **not necessary** to read all details in the second document if you already understand what to do or how to do.

### Implementation
- If you're unable to run ArcGIS Pro on your personal computer — for example, if you're using macOS, an older version of Windows, or your system doesn't meet the memory requirements — 
we strongly recommend completing the exercise in the **PC lab**.
- After finishing your work, please compress your project files or folders and submit them via Moodle.
    - 📌 The file should be named like: Exercise0_Your Name
- You only need to submit the compulsory part of the exercise — optional tasks are for practice only.
- You're also welcome to try completing the task using QGIS?.


---

## Task
### Overview
- [ ] **Install ArcGIS Pro** on your personal computer (Windows only, or via a virtual machine on macOS/Linux).
- [ ] Learn how to log in to the **TUM PC lab** and launch ArcGIS Pro from there
- [ ] Download the raw data from Moodle and **save your work to your TUM WebDisk**(his way, you can access your files from any device, anywhere.).
- [ ] Follow proper naming conventions when creating folders and files for your project. 

### Descriptions
Detailed instructions in {download}`Lesson 0 <../doc/Lesson 0.docx>`
[Click here to look](./lessons/lesson0.md)

#### Data 
- Data-students.gdb

### Optional Task
- For principle:
    - What is _.gbd_?
- For Python: 
    - Create a [virtual environment](https://www.w3schools.com/python/python_virtualenv.asp) where you can install the required geospatial libraries (e.g. geopandas, shapely, scikit-learn, etc.).
        - 💡 We recommend using modern Python packaging tools such as [Conda](https://www.anaconda.com/docs/getting-started/miniconda/main), [Poetry](https://python-poetry.org/), or [uv](https://github.com/astral-sh/uv) to manage your environment and dependencies more efficiently.
    - Import and use them in your scripts.
- For C++:
    - Download and install GDAL, and make sure to link it correctly to your project.
        -  💡 We strongly recommend using [Docker](https://www.docker.com/) to manage dependencies and avoid complex configuration issues on your host system.
- For Front-End:
    - Use [npm](https://www.w3schools.com/whatis/whatis_npm.asp) to create a web application with [Openlayers](https://openlayers.org/) official templates.
    ```bash
    npm create ol-app my-map
    ```

## Materials
- [ArcGIS Pro help](http://pro.arcgis.com/en/pro-app/latest/help/main/welcome-to-the-arcgis-pro-app-help.htm)
- [Esri GIS @TUM](https://gis.ifm.ls.tum.de/Esri/stud/pro.php)
- [ArcGIS Pro, a video introduction](https://www.youtube.com/watch?v=vTcIquSnS-o&ab_channel=Esri)
- [Getting Started with ArcGIS Pro for Beginners](https://www.youtube.com/watch?v=hiFCPYqjam0&list=PLgxX4AQ_KUQ-Ixy4B1Fv_CFU62Gr1h3ya&ab_channel=TerraSpatial)
