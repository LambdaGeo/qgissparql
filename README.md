# QGISSPARQL

   [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23102044.svg)](https://doi.org/10.5281/zenodo.23102044)
   [![INPI Registered](https://img.shields.io/badge/INPI-RPC%20BR512026003805--7-004B87?style=flat&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCIgZmlsbD0id2hpdGUiPjxwYXRoIGQ9Ik0xMiAyQzYuNDggMiAyIDYuNDggMiAxMnM0LjQ4IDEwIDEwIDEwIDEwLTQuNDggMTAtMTBTMTcuNTIgMiAxMiAyem0wIDE4Yy00LjQxIDAtOC0zLjU5LTgtOHMzLjU5LTggOC04IDggMy41OSA4IDgtMy41OSA4LTggOHptLTUtOWgydjJoLTJ2LTJ6bTQgMGgydjJoLTJ2LTJ6bTQgMGgydjJoLTJ2LTJ6Ii8+PC9zdmc+)](https://www.gov.br/inpi/pt-br)

**QGISSPARQL** is a QGIS plugin that enables **bidirectional integration between Linked Data (RDF/SPARQL) and Geographic Information Systems (GIS)**.

It allows users to both:

* 🔽 **Import RDF data** from SPARQL endpoints into QGIS layers.
* 🔼 **Export GIS layers** into RDF triples (GeoSPARQL-compatible).

---

## 🚀 Overview

QGISSPARQL bridges the gap between the **Semantic Web** and **GIS workflows**, providing a unified environment to:

* Query SPARQL endpoints (e.g., Virtuoso, Apache Jena Fuseki).
* Load results directly as vector layers in QGIS.
* Convert geospatial layers into RDF triples.
* Publish or reuse data in Linked Data ecosystems.

Unlike traditional workflows that require scripts or intermediate formats, QGISSPARQL enables **end-to-end RDF ↔ GIS integration directly inside QGIS**.

---

## ✨ Features

### 🔽 Triple → Layer (Import)

* Query any SPARQL 1.1 endpoint.
* Integration with data.world datasets.
* Background execution (non-blocking tasks).
* Automatic geometry detection from WKT.
* Dynamic attribute mapping.

### 🔼 Layer → Triple (Export)

* Convert vector layers (point, line, polygon) to RDF.
* Turtle serialization support.
* URI generation strategies (UUID or attribute-based).
* Mapping of attributes to RDF vocabularies (GeoSPARQL, SKOS, Data Cube).
* Searchable URI selection with autocompletion.

### 🧠 Advanced Features

* Unified dock interface with tabs (Import / Export).
* Vocabulary loading (GeoSPARQL, DataCube, SKOS, FOAF).
* Persistent configuration (e.g., data.world API tokens).
* Intelligent mapping UI with preview of auto-generated URIs.

---

## 🖥️ Interface

The plugin provides a unified dock with two main tabs:

### 🔽 Triple → Layer (Import)
Execute SPARQL queries and load results into QGIS.

<p align="center">
  <img src="docs/images/dock_triple2layer.png" alt="Triple to Layer Interface" width="600">
</p>

### 🔼 Layer → Triple (Export)
Convert GIS layers into RDF triples.

<p align="center">
  <img src="docs/images/dock_layer2triple.png" alt="Layer to Triple Interface" width="600">
</p>

---

## 📦 Installation

### 1. Install Plugin

Clone or download this repository:

```bash
git clone https://github.com/LambdaGeo/qgissparql
```

Copy to your QGIS plugins directory:

* **Linux:** `~/.local/share/QGIS/QGIS3/profiles/default/python/plugins/`
* **Windows:** `%APPDATA%\QGIS\QGIS3\profiles\default\python\plugins\`

Restart QGIS and enable the plugin via:

> Plugins → Manage and Install Plugins

---

### 2. Install Python Dependencies

#### Linux

```bash
pip install pandas setuptools --break-system-packages
pip install datadotworld SPARQLWrapper rdflib --break-system-packages
```

#### Windows (OSGeo4W Shell)

```bash
pip install pandas setuptools datadotworld SPARQLWrapper rdflib
```

---

## 🔑 Authentication (data.world)

You can configure your API token in three ways:

1. **Inside QGIS plugin settings** (Save Token button in the dock).
2. **Environment variable:**

   ```
   DW_AUTH_TOKEN=your_token
   ```
3. **CLI configuration:**

   ```
   dw configure
   ```

---

## ▶️ Usage

### Import (Triple → Layer)

1. Open: `Vector → QGISSPARQL → Open Dock`.
2. Select Source type (SPARQL endpoint or data.world).
3. Write or load a SPARQL query (formatting and indentation are preserved).
4. Define geometry column (WKT).
5. Execute import.

---

### Export (Layer → Triple)

1. Select a vector layer.
2. Define Base namespace and ID attribute.
3. Map attributes to RDF properties (searchable).
4. Optionally load a vocabulary (GeoSPARQL, etc.).
5. Export to `.ttl`.

---

## 👥 Authors

* **Sérgio Souza Costa** — https://github.com/profsergiocosta
* **Nerval de Jesus Santos Junior** — https://github.com/nervaljunior
* **Felipe Martins Sousa**
* **José Magno Pinheiro Alves**
* **Denilson da Silva Bezerra**

**LambdaGeo Research Group**
Universidade Federal do Maranhão (UFMA)

---

## 📜 Registration and Intellectual Property

This software is an open-source project, but it holds an official intellectual property registration in Brazil, guaranteeing authorship and institutional ownership.

- **Issuing Body:** National Institute of Industrial Property (INPI), Brazil
- **Process No.:** BR512026003805-7
- **Titleholder:** Universidade Federal do Maranhão (UFMA)
- **Registered Authors:** Denilson da Silva Bezerra, Sérgio Souza Costa, Nerval de Jesus Santos Junior, Felipe Martins Sousa, José Magno Pinheiro Alves.
- **Creation Date:** 31/01/2023
- **Programming Language:** Python
- **Field of Application:** IF-07 (Information Technology)
- **Program Type:** UT-03 (Utility Software)
- **SHA-256 Hash Summary:** `0b0e506b0a607fcdd8f6c7f531bb3c68be2da662bdf9f681f43f8a95a97c1b23`

> 💡 **Note:** The INPI registration protects the expression of the code under national law, while the Zenodo DOI (above) facilitates international academic citation and scientific reproducibility of specific software versions.

## 📚 How to Cite

If you use QGISSPARQL in your research, please cite it using the official DOI:

> Costa, S. S., Bezerra, D. S., Santos Junior, N. de J., Sousa, F. M., & Alves, J. M. P. (2026). *QGISSPARQL* (Version X.X.X) [Computer software]. Universidade Federal do Maranhão. INPI Registration: BR512026003805-7. https://doi.org/10.5281/zenodo.YOUR_NUMBER_HERE

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Please check [CONTRIBUTING.MD](CONTRIBUTING.MD).

---

## 📜 License

MIT License
