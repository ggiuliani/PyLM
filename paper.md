---
title: 'PyLM: A Python implementation for Landscape Mosaic analysis'
tags:
- Python
- Jupyter
- land cover
- landscape
- environment
- ecology
- ecosystem services
date: "9 September 2025"
output: pdf_document
authors:
- name: Gregory Giuliani
  orcid: "0000-0002-1825-8865"
  corresponding: yes
  affiliation: '1, 2'
bibliography: paper.bib
affiliations:
- index: 1 
  name: Envirospace group, Institute for Environmental Sciences, University of Geneva, Geneva, Switzerland
- index: 2
  name: United Nations Environment Programme, GRID-Geneva, Geneva, Switzerland  
---

# Summary
[ describing the high-level functionality and purpose of the software for a diverse, non-specialist audience.]
Landscape analysis, ... however the only implementation available is in GTB
PyLM is a Python implementation of the Landscape Mosaic (LM) model originally developed by Vogt et al and Ritters et al.

It facilitates the analysis of Land Cover data to produce relevant metrics for Landscape assessment.

# Statement of need
[illustrates the research purpose of the software and places it in the context of related work.]

Landscapes are defined as mosaics of different land cover, land use, habitats,and ecosystems [REF]. Landscape ecology is a field of ecology that specifically examines the spatial patterns of ecosystems and the processes that shape them across heterogeneous environments [REF].  It emphasizes the relationships between spatial configuration (e.g., size, shape, distribution) and ecological dynamics including species movement, biodiversity, and ecosystem functioning [REF]. To quantify these spatial patterns, a variety of metrics are available to account for characteristics such as patch area, diversity, density, connectivty and fragmentation [REF Computational methods; PyLandStats, NLMpy].  These metrics serve as essential tools for conservation planning, habitat management, and sustainability research by providing a standardized way to analyze landscape structure, detect changes over time, and assess the impacts of natural disturbances or human activities like urbanization, agriculture, and deforestation.
To identify and assess spatial patterns, different methods are available enabling to monitor landscape's evolution and linking them to specific ecological processes [REF]. The Landscape Mosaic (LM) approach provides a framework for quantifying spatial heterogeneity by employing a tri-polar classification scheme based on three land cover classes [REF Ritters]. The method applies a moving window to quantify the relative proportions of the three classes within each focal grid cell. These proportions are subsequently assigned to one of 19 mosaic categories, determined by threshold criteria that capture the presence, dominance, or exclusivity of each classe. The LM approach is designed to characterize the spatial juxtaposition of anthropogenic land cover (i.e., developed and agricultural areas) relative to natural land cover. By simultaneously evaluating these three dominant land cover types, the approach captures landscape composition, connectivity, and heterogeneity, thereby providing an integrated measure of human influence on landscapes. The indicator assigns each location to a category based on the relative proportions of Agriculture, Natural, and Developed land within its surrounding neighborhood. This classification supports the quantification and spatial assessment of landscape capacities to sustainably supply ecosystem services [REF]. The Landscape Mosaic provides a framework for assessing the state, pressures, and temporal dynamics of landscapes, including the intensity of land use across agricultural, urban, and natural ecosystems, as well as their complex interactions under changing environmental and socio-economic conditions.

Currently, there is only on implementation available of the LM framework...

Only implementation available is in GuidosToolbox - Graphical User Interface for the Description of image Objects and their Shapes - GTB (https://doi.org/10.1080/22797254.2017.1330650). GTB is an suite of sotfware components mostly used for forestry.

There is a neeed for a standalone tool to could be closley connected to land cover monitoring tools such a Living Earth.

PyLM is therefore....

Integrated as an analytical module within the Living Earth framework

# Main modules
Linear process (each module the subsequant one)
(1) Initialization
(2) Input data + map conversion [optional]
(3) LM Analysis
(3.1) Moving window - 103 classes - 19 classes
(3.2) LM Background
(3.3) LM Diversity
(3.4) LM Agriculture
(3.5) LM Natural
(3.6) LM Developed
(3.7) LM Antthropic intensity

# Installation
Require Jupyter Notebook/Lab and Python 3.10 (minimal)
Copy the notebook in the folder

# Auhtor contributions
Gregory Giuliani authored the original version of the package, developed the pipeline and all of its functions, maintained the package, wrote the documentation, debugged the code, and contributed to the drafting of the article.

# Acknowledgements
The author would like to acknowledge the European Union ‘Horizon Europe Program’ that funded the LandShift (Grant Agreement no. 101182007) and the MONALISA (Grant Agreement no. 101157867) projects as well as the Swiss National Science Foundation that funded the DynamicLand project (Grant no. 221323) for their respective support.
The author acknowledge contributions from Lucie Schlumpf and Carole Planque for their help in testing the package. Their input and feedback were essential in identifying and resolving technical issues, ensuring the accuracy and reliability of the results.

# References