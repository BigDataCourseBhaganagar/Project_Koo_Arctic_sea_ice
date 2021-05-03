# Project_Koo_Arctic_sea_ice
- ME 5013 (Spring 2021) Big data analysis in extreme environments
- Final project done by Younghyun Koo (younghyun.koo@utsa.edu): monitoring of Arctic sea ice concentration and extent using AMSR passive microwave satellite data

## 1. Introduction
  Sea ice is an important indicator of recent global climate change. According to many previous studies, the extent and thickness of sea ice has been decreased continuously during last few decades. In particular, the Arctic sea ice has been decreased much faster than the Antarctic. In this project, I will examine the spatiotemporal variations of sea ice extent (SIE) over the Arctic by using spaceborne remote sensing data. Passive microwave (PMW) sensors have been actively used for monitoring of sea ice extent due to its advantages in data availability regardless of weather conditions or time. I will use one of the representative PMW sensors called AMSR (Advanced Microwave Scanning Radiometer) to characterize the spatiotemporal variations of Arctic sea ice extent from 2012 to present.
  
## 2. Data
The AMSR (Advanced Microwave Scanning Radiometer) data are available via National Snow & Ice Data Center (NSIDC) website (https://nsidc.org/data/AU_SI25/versions/1). This product is available from July 2012, so about 3,200 files (~40 MB per each file, total ~128 GB) are available. Due to the authorization issue for the access to the NASA Earthdata, I coulnd not access to this data remotely, but I downloaded all of the data by using Python code for bulk downloads.

## 2. Code capabilities
Jupyter notebook file named "SIC_northern.ipynb" performs the following functions:
### (1) Read AMSR sea ice concentration data (.h5 format)
### (2) Mapping of sea ice concentration
### (3) Temporal analysis of sea ice extent (SIE)
### (4) Dendrogram
- Draw and analyze dendrograms to figure out the hierarchical structure of SIE by region and time.
### (5) Principal component analysis (PCA)


Following Python packages are required to run this notebook file successfully.
- h5py: read hdf files
- pandas: organize the data into dataframe by time and by region
- numpy: read hdf files and variables as numpy arrays
- matplotlib: plot and map the result
- astrodendfro: plot and analyze dendrograms
- scikit-learn: conduct PCA analysis


