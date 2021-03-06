Global protected areas
=================================================
[![DOI](https://zenodo.org/badge/18940/paleo13/global-protected-areas.svg)](https://zenodo.org/badge/latestdoi/18940/paleo13/global-protected-areas)

[Jeffrey O. Hanson](https://wwww.jeffrey-hanson.com)

Correspondence should be addressed to [jeffrey.hanson@uqconnect.edu.au](mailto:jeffrey.hanson@uqconnect.edu.au)

-----

This repository contains source code for automatically downloading, cleaning, and processing the [World Database on Protected Areas](http://www.protectedplanet.net/). By using this repository, users can maintain an up to date version of the world's protected areas.

Briefly, the following operations are run in sequence using [ESRI ArcGIS](https://www.esri.com/software/arcgis):

1. raw data is downloaded
2. geometry issues are resolved
3. invalid areas are omitted from the dataset
4. protected areas are reprojected to a projected coordinate system
5. protected areas are simplified to reduce computation burden
6. protected areas only represented as points are buffered and merged with polygons
7. areas contained in multiple protected areas are assigned the best IUCN criteria that overlaps with them
8. slivers are removed from the dataset
8. protected areas are exported in shapefile and raster format

This program has several dependencies. To install them, please see [INSTALL.md](https://github.com/paleo13/global-protected-areas/blob/master/INSTALL.md). 

To run all computational analyses: Double click on `run.bat` or type `make all` into the command prompt. The final shapefile and raster files will appear in the directory when processing has completed. The numbers in the raster correspond to the following IUCN categories: IA (0), IB (1), II (2), III (3), IV (4), V (5), VI (6), Not Assigned (7), Not Applicable (8), Not Reported (9). Pixels that are not protected areas have Missing Data values.

*Note that all parameters can be customized by altering files in the code/parameters folder.* 

-----

### Repository overview

* data
	+ _raw_: raw data downloaded form [protected planet](http://www.protectedplanet.net/)
	+ _intermediate_: data generated during processing
	+ _final_: final cleaned dataset
* code
	+ _parameters_: files used to customise analysis in [TOML format](https://github.com/toml-lang/toml)
	+ [_python_](https://www.python.org): scripts used to run the analysis 

### Software

* Operating system
	+ Windows (7+)
* Programs
	+ ArcGIS (version 10.3+)
	+ GNU make
	+ pip
* Python packages
	+ arcpy (installed automatically with ArcMAP)
	+ toml
	+ wget

-----

### If you used this program in your paper, please cite it.

Hanson J. O. (2016). Global protected areas. version 1.0.1. doi: 10.5281/zenodo.35031.
