# Project_Koo_Arctic_sea_ice
- ME 5013 (Spring 2021) Big data analysis in extreme environments
- Final project done by Younghyun Koo (younghyun.koo@utsa.edu): monitoring of Arctic sea ice concentration and extent using AMSR passive microwave satellite data

## 1. Introduction

## 2. Data
The AMSR (Advanced Microwave Scanning Radiometer) data are available via National Snow & Ice Data Center (NSIDC) website (https://nsidc.org/data/AU_SI25/versions/1). This product is available from July 2012, so about 3,200 files (~40 MB per each file, total ~128 GB) are available. Due to the authorization issue for the access to the NASA Earthdata, I coulnd not access to this data remotely, but I downloaded all of the data by using Python code for bulk downloads.

## 2. Code capabilities
Jupyter notebook file named "SIC_northern.ipynb" performs the following functions:
### (1) Read AMSR sea ice concentration data (.h5 format)
### (2) Mapping of sea ice concentration
### (3) Temporal analysis of sea ice extent (SIE)
### (4) Dendrogram
- Draw and analyze dendrograms to figure out the hierarchical structure of SIE by region and time.

Following Python packages are required to run this notebook file successfully.
- h5py: read hdf files
- pandas: organize the data into dataframe by time and by region
- numpy: read hdf files and variables as numpy arrays
- matplotlib: plot and map the result
- astrodendfro: plot and analyze dendrograms
- scikit-learn: conduct PCA analysis


