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

PyLM is a Python implementation of the Landscape Mosaic (LM) model originally developed by Vogt et al and Ritters et al.

It facilitates the analysis of Land Cover data to produce relevant metrics for Landscape assessment.

# Statement of need
Landscapes are defined as mosaics of different land cover, land use, habitats,and ecosystems [REF]. Landscape ecology is a field of ecology that specifically examines the spatial patterns of ecosystems and the processes that shape them across heterogeneous environments [REF].  It emphasizes the relationships between spatial configuration (e.g., size, shape, distribution) and ecological dynamics including species movement, biodiversity, and ecosystem functioning [REF]. To quantify these spatial patterns, a variety of metrics are available to account for characteristics such as patch area, diversity, density, connectivty and fragmentation [REF Computational methods; PyLandStats, NLMpy].  These metrics serve as essential tools for conservation planning, habitat management, and sustainability research by providing a standardized way to analyze landscape structure, detect changes over time, and assess the impacts of natural disturbances or human activities like urbanization, agriculture, and deforestation.
To identify and assess spatial patterns, different methods are available enabling to monitor landscape's evolution and linking them to specific ecological processes [REF]. The Landscape Mosaic (LM) approach provides a framework for quantifying spatial heterogeneity by employing a tri-polar classification scheme based on three land cover classes [REF Ritters]. The method applies a moving window to quantify the relative proportions of the three classes within each focal grid cell. These proportions are subsequently assigned to one of 19 mosaic categories, determined by threshold criteria that capture the presence, dominance, or exclusivity of each classe. The LM approach is designed to characterize the spatial juxtaposition of anthropogenic land cover (i.e., developed and agricultural areas) relative to natural land cover. By simultaneously evaluating these three dominant land cover types, the approach captures landscape composition, connectivity, and heterogeneity, thereby providing an integrated measure of human influence on landscapes. The indicator assigns each location to a category based on the relative proportions of Agriculture, Natural, and Developed land within its surrounding neighborhood. This classification supports the quantification and spatial assessment of landscape capacities to sustainably supply ecosystem services [REF]. The Landscape Mosaic provides a framework for assessing the state, pressures, and temporal dynamics of landscapes, including the intensity of land use across agricultural, urban, and natural ecosystems, as well as their complex interactions under changing environmental and socio-economic conditions.
Currently there is only one implementation of the LM framework within the GuidosToolbox (Graphical User Interface for the Description of image Objects and their Shapes - GTB) [REF]. GTB is a free and open-source software with a set of customized and thematicall grouped raster image processing routines mostly used in environmental, ecological, forestry, land cover / land use, and landscape‐ecology contexts. It is available through a Desktop application, for Windows, Mac and Linux as well as a command-line Linux server application for mass processing (GuidosToolbox Workbench GWB). Despite the fact that the LM model is available as single tool within GTB/GWB, it's interaction with other software/models is limited and therefore there is a need for having a version that could be available (1) as a standalone tool, (2) that could be executed both on a desktop or a server, (3) that could be easily embedded in processing chains/workflows or integrated in other analytical framework like LivingEarth [REF], (4) based on common data science language such as Python.
Based on these considerations, PyLM provides a Python implementation of the Landscape Mosaic model enabling users to process any land cover map and generate the different stratification layers as well as relevant statistics (e.g., heatmap). PyLM offers increased accessibility, flexibility, and computational power for landscape ecology, allowing for easier analysis, customization, and integration with other open-source tools for research, conservation, and planning. PyLM could be executes either as a standalone Python script, within a Jupyter Notebook environment, and ultimately could be easily embbeded in any processing workflow. Overall PyLM simplifies the production of key landscape metrics necessary for environmental monitoring.

# Main modules
Linear process (each module the subsequant one) (see for modules description: https://publications.jrc.ec.europa.eu/repository/handle/JRC120383)
(1) Initialization
(2) Input/Output data + map conversion [optional]
(3) LM Analysis
(3.1) Moving window - 103 classes - 19 classes
(3.2) LM Background
(3.3) LM Diversity
(3.4) LM Agriculture
(3.5) LM Natural
(3.6) LM Developed
(3.7) LM Antthropic intensity
(3.8) Heatmap

# Installation
Require Jupyter Notebook/Lab and Python 3.10 (minimal)
Copy the notebook in the folder

# Auhtor contributions
Gregory Giuliani authored the original version of the package, developed the pipeline and all of its functions, maintained the package, wrote the documentation, debugged the code, and contributed to the drafting of the article.

# Acknowledgements
The author would like to acknowledge the European Union ‘Horizon Europe Program’ that funded the LandShift (Grant Agreement no. 101182007) and the MONALISA (Grant Agreement no. 101157867) projects as well as the Swiss National Science Foundation that funded the DynamicLand project (Grant no. 221323) for their respective support.
The author acknowledge contributions from Lucie Schlumpf and Carole Planque for their help in testing the package. Their input and feedback were essential in identifying and resolving technical issues, ensuring the accuracy and reliability of the results.

# References