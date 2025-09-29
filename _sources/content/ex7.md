# E7: Network Analysis

## Warm Up
### Graph Theory & Graph Neural Networks

Closely related to **network analysis** are the fields of **graph theory** and **graph neural networks (GNNs)**.  

Graph theory originates from the famous **Königsberg Seven Bridges Problem** proposed by Euler in the 18th century. He asked whether it was possible to walk through the city of Königsberg and cross each of its seven bridges exactly once. 
Although the answer was “no,” this puzzle laid the foundation for graph theory — the mathematical study of **nodes (vertices)** and **edges (links)**.  
![Seven Bridges Problem](../images/ex7/Konigsberg_bridges.png "The illustration of Königsberg Bridge problem")

> In graph theory, a tree is essentially a special kind of graph — one that is connected and contains no cycles.

Building upon graph theory, **Graph Neural Networks (GNNs)** extend deep learning to irregular data structured as graphs. 
Instead of images or sequences, GNNs learn from graph-structured inputs where relationships matter as much as individual features. 
Applications include:  
- *Traffic prediction* (modeling flow and congestion on road networks).  
- *Social and spatial interaction modeling* (spread of diseases, information, or urban activity).  

Thus, from Euler’s simple bridge puzzle to today’s deep learning methods, graph-based thinking continues to provide powerful tools for analyzing, predicting, and optimizing complex spatial networks.  

### Shortest Path in a Network
One scientist once described this iconic problem by saying: “The shortest path is a beautiful problem that anyone in the world can understand.” 

You have learned **Dijkstra’s algorithm** in the lecture — the most famous and classical shortest-path algorithm that is widely used in daily applications. 
In 2024, it was even proved to have **Universal Optimality** (meaning that a single algorithm can run as fast as possible on *any* graph topology) in [this paper](https://arxiv.org/abs/2311.11793). Interestingly, in 2025 researchers reported an even faster approach. If you are a mathematical genius, you can take a look at [this paper](https://arxiv.org/abs/1808.10658) — though honestly, I couldn’t understand it myself. 😅

### Measure “importance” in a network
- **Degree Centrality**: Measures how many direct connections a node has.  
  - "It’s not what you know, it’s who you know." — a node with high degree is the social butterfly of the network.  

- **Closeness Centrality**: Quantifies how close a node is to all others in terms of shortest paths.  
  - Think of it as *how quickly you can spread gossip* across the entire network.  

- **Betweenness Centrality**: Counts how often a node lies on shortest paths between others.  
  - These are the *gatekeepers* or *bridges* of the network — remove them, and communities fall apart.  

- **Eigenvector Centrality**: Goes beyond simple degree: a node is important if it connects to other important nodes.  
  - "Tell me who your friends are, and I will tell you who you are." — proverb perfectly captures this idea.  
  - Famous example: Google’s **[PageRank](https://en.wikipedia.org/wiki/PageRank)** is a variant of eigenvector centrality. A similar idea also can be found in **[word2vec](https://www.tensorflow.org/text/tutorials/word2vec)**.

- **Rich-Club Coefficient**: Describes the tendency of highly connected nodes to also connect with each other, forming an "elite club." 

## Task
In this exercise, you will practice several **fundamental network analysis methods** in ArcGIS Pro.  
The goal is to understand how networks can be built from road data and analyzed for accessibility, connectivity, and routing problems.  

### Overview
- [ ] **Build a network dataset**  
  - preprocess OSM road data, clean topology, and configure travel modes (e.g., walking).  
- [ ] **Explore the network**  
  - check connectivity and attributes using the Explore Network tool.  
- [ ] **OD Cost Matrix**  
  - calculate travel distances between origin and destination points.  
- [ ] **Shortest Route**  
  - find the optimal path between multiple stops using Dijkstra’s algorithm.  
- [ ] **Traveling Salesman Problem**  
  - compute the shortest tour visiting all given stops.  
- [ ] **Isochrones (Service Areas)**  
  - construct reachable areas (e.g., 5-min walk) around transport stops.  

---

### Descriptions & Steps
Detailed instructions in {download}`Lesson 7 <../doc/Lesson 7.docx>`

& You can [Click here to look](./lessons/lesson7.md)

#### Data
- `Data Students.gdb`

#### 1. Build the Network Dataset
- Create a new feature dataset in the geodatabase.  
- Preprocess OSM roads: fix overshoots/undershoots, remove pseudo-nodes, handle overpasses.  
- Configure cost attributes (e.g., length in meters) and build the network.  

#### 2. Explore the Network
- Use the **Explore Network** tool to check connectivity and ensure topology is valid.  

#### 3. OD Cost Matrix
- Select multiple origins and destinations.  
- Generate a cost matrix showing travel distance between each pair.  

#### 4. Shortest Route
- Add stops along the network.  
- Run the shortest path solver to find optimal routes.  

#### 5. Traveling Salesman Problem
- Input multiple stops (unordered).  
- Calculate the shortest tour that visits all of them once.  

#### 6. Isochrones (Service Areas)
- Define transport stops as facilities.  
- Generate service areas for 5, 10, 15 minutes walking distance.  
- Visualize and compare reachability zones.  


### Optional Task
- Explore network analysis in your programming environment. You can start with these examples:  
  - [Introduction to Network Analysis in Python](https://trenton3983.github.io/posts/intro-network-analysis/)  
  - [Automating GIS: Network analysis in Python](https://autogis-site.readthedocs.io/en/latest/lessons/lesson-6/network-analysis.html)  
  - [Exploring and Analyzing Network Data with Python](https://programminghistorian.org/en/lessons/exploring-and-analyzing-network-data-with-python)  

- Build your own interactive web map:  
  - Choose two locations and compute the **shortest path** using a web map service.  
  - Set different travel modes (car, bicycle, or foot) and compare routes.  
  - Select one location, define a radius, and **visualize the buffer area** on the map.



## Materials
- [A Gentle Introduction To Graph Theory, Vaidehi Joshi](https://medium.com/basecs/a-gentle-introduction-to-graph-theory-77969829ead8)
- [Network Analyst tutorials, ArcGIS Pro Documentation](https://pro.arcgis.com/en/pro-app/latest/help/analysis/networks/network-analyst-tutorials.htm)
- [What is Network Analysis? Mengsay Loem](https://medium.com/data-science/network-analysis-d734cd7270f8)
- [Lesson: Network Analysis, QGIS](https://docs.qgis.org/3.40/en/docs/training_manual/vector_analysis/network_analysis.html)
