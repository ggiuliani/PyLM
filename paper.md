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
The need of landscape mosaic

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
Require Jupyter Notebook/Lab and Python 3.XX
Copy the notebook in the folder

# Auhtor contributions
Gregory Giuliani authored the original version of the package, developed the pipeline and all of its functions, maintained the package, wrote the documentation, debugged the code, and contributed to the drafting of the article.

# Acknowledgements
SNF DynamicLand; EC Horizon-Europe MONALISA & LandShift

# References
