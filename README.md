# PyLM - Python Landscape Mosaic model
A Python implementation of the Landscape Moscai model

## Installation
This package requires Python 3.10 or later and JupyterLab either on a [server](https://jupyter.org/install) or on a [desktop](https://github.com/jupyterlab/jupyterlab-desktop). It also requires the following packages: 
`rasterio`, `numpy`, `scipy`, and `csv`. These dependencies are automatically verified (and installed) within the <i>Intialization</i> module.

## Main modules
The analytical workflow follows a linear architecture, in which the output of each module constitutes the input for the subsequent module. Hereafter, we present the main modules and their respective tasks: 

- `(1) Initialization`: This module first test if the necessary librairies are installed and then user is able to define both input and output folders.
- `(2) 'Input data`: reads and provides information on the input raster map with no more than 3 target classes having the assignment AND (1 Byte - Agriculture, 2 Byte - Natural, 3 Byte - Developed) plus an optional class value of 0 Byte which is reserved for masking missing/no-data pixels. 
- `(2.1) Map conversion [optional]`: Depending on the LUC used, this modules gives the flexibility to reclassify any land cover/use (LUC) map to the 3-class raster map required by the LM model.
- `(3) LM Analysis`: This the main module that computes first the proportion of A-N-D per pixel, then produces the 103 classes and 19 classes following [riitters_indicator_2009, vogt_revisiting_2024] \autoref{fig1}, and finally generates all the stratification layers \autoref{fig2}.
- `(3.1) Moving window - 103 classes - 19 classes`: This sub-module computes the propostion of A-N-D classes on a per pixel basis and then computes the 103 classes and aggregates to 19 classes.
- `(3.2) LM Background`: summarizes the LM into 4 classes Natural - Agriculture - Developed - Mixed, showing the dominant presence of each LUC classes.
- `(3.3) LM Diversity`: summarizes the LM into 4 classes to account the increasing degree of LUC diversity from Uniform, Dual, Triple, or Intermixed LUC, reporting on the degree of spatial heterogeneity.
- `(3.4) LM Agriculture`: summarizes the LM into 3 classes showing where agricultural LUC is dominant (>=60%), subdominant, or minor (<10%), thereby enabling the determination of the anthropogenic impact from agriculture.
- `(3.5) LM Natural`: summarizes the LM into 3 classes showing where natural LUC is dominant (>=60%), subdominant, or minor (<10%), allowing to determine the dominant natural classes not impacted by anthropogenic activies.
- `(3.6) LM Developed`: summarizes the LM into 3 classes showing where developed LUC is dominant (>=60%), subdominant, or minor (<10%), allowing to determine the anthropogenic impact from urbanization.
- `(3.7) LM Anthropic intensity`: summarizes the anthopic intensity into 6 classes from Very Low - Low - Medium - High - Very High - Extreme, to account for the anthropogenic impacts.
- `(3.8) Heatmap`: provides summary statistics of the frequency distribution of the 103-classes within the ternary diagram.

![Output of module 3.1 showing the 19 classes map for the entire Switzerland.\label{fig1}](img/figure1.png)

![The five stratification layers produced for the entire Switzerland.\label{fig2}](img/figure2.png)

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
