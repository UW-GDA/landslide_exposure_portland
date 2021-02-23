Landslide Exposure of Building Infrastructures in Portland, OR
=======

**Daniel Acosta**

Final Project: UW Geospatial Data Analysis  
CEE498/CEWA599  
Instructor: David Shean  

Overview
-----------
This project measures the landslide exposure of buidling infrastructures in Portland, Oregon, using landslide susceptibility maps retrieved from SLIDO and OpenStreetMap data processed to derive building footprint maps.

## Background
Based on the quantitative landslide risk equation, which is defined as risk as a function of annual probability of landslide (hazard), the spatial and spatial-time probability of a landslide impacting a building (runout and exposure), and the probability of injury or death from a given impact by a landslide (vulnerability). In this sense, a landslide exposure is defined as the analysis of elements at risk of being prone to a hazardous zone. The elements at risk refer to building footprints that match specific susceptibility classes. 

Given a landslide susceptibility map, often landslide exposure has been measured using land cover maps for further risk assessment. However, a detailed landslide exposure analysis using building footprint maps is scarce. For this reason, this project explores some ways building footprint data can be utilized to assess landslide exposure in Portland, Oregon, with a focus on building infrastructures. Further research can include social and economical features of the building zones. 

## Problem Statement
What is the landslide exposure of building infrastructure in the city of Portland, Oregon?
The dataset to be used are:
* [Landslide Susceptibility maps](https://www.oregongeology.org/slido/data.htm)
* [Building Footprint data](https://github.com/Microsoft/USBuildingFootprints)

## Methodology/Approach

The simple method to quantify landslide exposure is by overlapping the susceptibility map with the building footprint and measure how much raster area corresponds to each susceptibility class.

**Tools packages (libraries):**
import os  
import requests  
import numpy as np  
import pandas as pd  
import geopandas as gpd  
import rasterio as rio  
from rasterio import plot, mask  
from rasterio.warp import calculate_default_transform, reproject, Resampling  
import matplotlib.pyplot as plt  
import rasterstats  

## References
W. Pollock, J. Wartman, G. Abou-Jaoude, A. Grant, (2019). Risk at the margins: A natural hazards perspective on the Syrian refugee crisis in Lebanon, International Journal of Disaster Risk Reduction, Volume 36, 101037, ISSN 2212-4209, https://doi.org/10.1016/j.ijdrr.2018.11.026.

C. Promper, Ch. Gassner, T. Glade, (2015). Spatiotemporal patterns of landslide exposure – a step within future landslide risk analysis on a regional scale applied in Waidhofen/Ybbs Austria, International Journal of Disaster Risk Reduction, Volume 12,  Pages 25-33, ISSN 2212-4209, https://doi.org/10.1016/j.ijdrr.2014.11.003.