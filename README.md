# 🧬 Synthetic Vascular Networks

Example binary segmentations of synthetic vascular networks for testing skeletonization, connectivity, and topology-aware metrics.

These datasets provide **controlled geometries with known structure**, allowing evaluation of skeletonization methods independently of imaging noise or segmentation uncertainty.

---
<br><br>
## 📂 Datasets

### 🌿 Synthetic Tree
Hierarchical tree-like vascular network generated using stochastic L-systems.  
Exhibits structured branching with minimal loop formation.

* **Properties:**
  * Tree topology 
  * Variable vessel diameters and lengths
  * Boundary-intersecting vessels (cropped subvolume)

* **File:** `SyntheticTree.tif`

---

### 🕸️ Synthetic Mesh
Loop-rich vascular network derived from intersecting branches of L-system trees and additional manual connectivity edits.  
Designed to mimic capillary-like redundancy and complex topology.

* **Properties:**
  * High loop density
  * Multiple interconnections between segments
  * Single connected component

* **File:** `SyntheticMesh.tif`

---

### 🔁 Synthetic Tree (Loop-Modified)
Modified version of the synthetic tree network with **manually introduced loops**.  
Used to evaluate sensitivity to topological errors such as artificial reconnections or missed loops.

* **Properties:**
  * Tree-derived structure
  * Controlled loop insertion (5 loops added)
  * Hybrid topology (between tree and mesh)

* **File:** `SyntheticTree_LoopModified.tif`

---
<br><br>
## 🧭 Intended Use

These datasets are designed for:

* 🔍 Skeletonization benchmarking  
* 🔗 Connectivity validation  
* 🔄 Loop detection and topological analysis  
* 📊 Metric evaluation (e.g. Euler characteristic, bifurcation accuracy)

They can be used alongside:
* Binary image-based analysis pipelines (`.tif`)
* Spatial graph / skeletonization outputs (`.am`)

---
<br><br>
## ⚙️ Generation Overview

The synthetic tree network was generated using a stochastic L-system framework (**V-System**), which models vessel growth using probabilistic branching rules and geometry construction.

The mesh network was created by:
* selecting intersecting regions from later-generation trees  
* increasing loop density via subvolume combination  
* manually introducing additional interconnections  

No smoothing, pruning, or post-generation correction was applied.  
All datasets are provided directly as **binary voxel volumes**.

---
<br><br>
## 📦 Data Format

* **Type:** 3D binary segmentation  
* **Format:** `.tif`  
* **Voxel space:** isotropic voxel grid  
* **Convention:** `[Z, Y, X]`

---
<br><br>
## 🔗 Synthetic Network Generation

The synthetic tree networks were generated using the **V-System** framework, a stochastic L-system-based approach for vascular network modelling.

* **Repository:** https://github.com/psweens/V-System  
* **Version used:** 2.0  

This framework enables generation of hierarchical vascular networks with controllable branching, diameter variation, and stochastic geometry.

> 💡 If you want to generate your own synthetic vascular networks, this repository provides the full implementation and parameter control.

---
<br><br>
## 🧾 Attribution

Synthetic tree networks in this dataset were generated using the V-System framework developed by the original authors.  
Mesh-like and loop-modified networks were derived from these outputs with additional subvolume selection and manual connectivity edits.

---
<br><br>
## 🧾 Notes

* 🧠 These datasets isolate **structural errors** from imaging artefacts  
* 🎯 Useful for testing failure modes such as:
  * fragmentation  
  * missed connections  
  * false loops  
  * incorrect bifurcation detection  

---
<br><br>
## 📌 Citation

If you use these datasets in academic work, please cite the associated methodology and reference this repository.
