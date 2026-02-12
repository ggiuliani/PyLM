# PyLM - Python Landscape Mosaic model
PyLM is a Python implementation of the Landscape Mosaic model for processing land cover maps, generating stratification layers, and producing key landscape metrics and visualizations (e.g., heatmaps). It is designed for accessibility, flexibility, and integration with open-source tools, supporting use as a standalone script, in Jupyter Notebooks, or within larger workflows for research, conservation, and planning.

## Installation
This package requires Python 3.10 or later and JupyterLab (server or desktop). It also requires the following packages: 
`rasterio`, `numpy`, `scipy`,  `matplotlib` and `csv`. These dependencies are automatically verified (and installed) within the <i>Intialization</i> module.

Once the release downloaded and the zip file extracted, user can edit the python file (or the Jupyter NoteBook file) to define to define the input (i.e., where the input LUC map in geotiff format is stored - `inputFolder`) and output (i.e., where all produced layers will be stored - `outputFolder`) folders. In addition, users can also edit the filename of the LUC map in the `l3` variable. Then simply execute the command `python PyLM.py` and once process all layers are available in the output folder. Altneratively, users can execute the Jupyter NoteBook provided in the release.

## Main modules
The analytical workflow follows a linear architecture, in which the output of each module constitutes the input for the subsequent module. Hereafter, we present the main modules and their respective tasks: 

- `Initialization`: This module first test if the necessary librairies are installed and then user is able to define both input and output folders.
- `Input data`: reads and provides information on the input raster map with no more than 3 target classes having the assignment AND (1 Byte - Agriculture, 2 Byte - Natural, 3 Byte - Developed) plus an optional class value of 0 Byte which is reserved for masking missing/no-data pixels. 
- `Map conversion [optional]`: Depending on the LUC used, this modules gives the flexibility to reclassify any land cover/use (LUC) map to the 3-class raster map required by the LM model.
- `LM Analysis`: This the main module that computes first the proportion of A-N-D per pixel, then produces the 103 classes and 19 classes following [riitters_indicator_2009, vogt_revisiting_2024], and finally generates all the stratification layers.
- `Moving window - 103 classes - 19 classes`: This sub-module computes the propostion of A-N-D classes on a per pixel basis and then computes the 103 classes and aggregates to 19 classes.
- `LM Background`: summarizes the LM into 4 classes Natural - Agriculture - Developed - Mixed, showing the dominant presence of each LUC classes.
- `LM Diversity`: summarizes the LM into 4 classes to account the increasing degree of LUC diversity from Uniform, Dual, Triple, or Intermixed LUC, reporting on the degree of spatial heterogeneity.
- `LM Agriculture`: summarizes the LM into 3 classes showing where agricultural LUC is dominant (>=60%), subdominant, or minor (<10%), thereby enabling the determination of the anthropogenic impact from agriculture.
- `LM Natural`: summarizes the LM into 3 classes showing where natural LUC is dominant (>=60%), subdominant, or minor (<10%), allowing to determine the dominant natural classes not impacted by anthropogenic activies.
- `LM Developed`: summarizes the LM into 3 classes showing where developed LUC is dominant (>=60%), subdominant, or minor (<10%), allowing to determine the anthropogenic impact from urbanization.
- `LM Anthropic intensity`: summarizes the anthopic intensity into 6 classes from Very Low - Low - Medium - High - Very High - Extreme, to account for the anthropogenic impacts.
- `Heatmap`: provides summary statistics of the frequency distribution of the 103-classes within the ternary diagram.

![Output of module 3.1 showing the 19 classes map for the entire Switzerland.\label{fig1}](img/figure1.png)

![The six stratification layers produced with PyLM for the entire Switzerland.\label{fig2}](img/figure2.png)

## Test
The dependencies are automatically verified (and installed) within the <i>Intialization</i> module.

## Contributor guidelines
Contributions are welcome and greatly appreciated! To contribute, please follow the following guidelines:

**Reporting issues**
* Check that the issue has not already been reported on the [issue tracker](https://github.com/ggiuliani/PyLM/issues).
* Submit an issue on the [issue tracker](https://github.com/ggiuliani/PyLM/issues).

**Development process**
* Fork the repository, make changes in your fork, and submit a pull request.
* Follow the existing coding style and structure.
* Write tests for any new functionality.
* Document any changes in the package documentation.

**Where to get help**
* Maintainer: [Gregory Giuliani](https://www.unige.ch/envirospace/people/giuliani)

**How to cite?**
<br>Giuliani G. (2026) PyLM: A Python implementation for Landscape Mosaic analysis, Land 15(1):187 https://doi.org/10.3390/land15010187
