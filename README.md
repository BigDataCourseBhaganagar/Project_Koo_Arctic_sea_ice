# Statistical Analysis of Sea Ice Extent in the Arctic Ocean using AMSR Passive Microwave Data
- ME 5013 (Spring 2021) Big data analysis in extreme environments
- Final project done by Younghyun Koo (younghyun.koo@utsa.edu): monitoring of Arctic sea ice concentration and extent using AMSR passive microwave satellite data
- Last update: May 03 2021

## 1. Introduction
  Sea ice is an important indicator of recent global climate change. According to many previous studies, the extent and thickness of sea ice has been decreased continuously during last few decades. In particular, the Arctic sea ice has been decreased much faster than the Antarctic. In this project, I will examine the spatiotemporal variations of sea ice extent (SIE) over the Arctic by using spaceborne remote sensing data. Passive microwave (PMW) sensors have been actively used for monitoring of sea ice extent due to its advantages in data availability regardless of weather conditions or time. I will use one of the representative PMW sensors called AMSR (Advanced Microwave Scanning Radiometer) to characterize the spatiotemporal variations of Arctic sea ice extent from 2012 to present.
  
## 2. Data
The AMSR (Advanced Microwave Scanning Radiometer) data are available via National Snow & Ice Data Center (NSIDC) website (https://nsidc.org/data/AU_SI25/versions/1). This product is available from July 2012, so about 3,200 files (~40 MB per each file, total ~128 GB) are available. Due to the authorization issue for the access to the NASA Earthdata, I coulnd not access to this data remotely, but I downloaded all of the data by using Python code for the bulk downloads (see nsidc-download_AU_SI25.001_2021-04-28.py).

## 2. Code capabilities
Jupyter notebook file named "SIC_northern.ipynb" performs the following functions:
### (1) Read AMSR sea ice concentration data (.h5 format)
- Read .h5 files as numpy arrays (size: (448, 304, 3175))
### (2) Mapping of sea ice concentration
- Draw yearly/monthly maps of Arctic sea ice concentration
![](/images/SIC_maps.png)
### (3) Temporal analysis of sea ice extent (SIE)
- Yearly/monthly trend of sea ice extent for the Arctic region and 10 sub-regions
- Fourier transform to understand period trend of SIE
![](/images/temporal_analysis.png)
### (4) Dendrogram
- Draw and analyze dendrograms to figure out the hierarchical structure of SIE by region and time.
![](/images/Demdrograms.png)
### (5) Statistical moments (skewness and kurtosis)
- Draw and analyze skeness and kurtosis of SIE with various smooth size
### (5) Principal component analysis (PCA)
- Reduce dimensions of SIC data by using PCA components
![](/images/PCA.png)

## 3. Necessary Python packages
Following Python packages are required to run this notebook file successfully.
- h5py: read hdf files (https://pypi.org/project/h5py/)
- pandas: organize the data into dataframe by time and by region (https://pandas.pydata.org/)
- numpy: read hdf files and variables as numpy arrays (https://numpy.org/)
- matplotlib: plot and map the result (https://matplotlib.org/)
- astrodendro: plot and analyze dendrograms (https://dendrograms.readthedocs.io/en/stable/)
- scikit-learn: conduct PCA analysis (https://scikit-learn.org/stable/)

## 4. Hypothesis
According to many previous studies and papers, the Arctic sea ice extent has been decreased during last few decades. By using AMSR sea ice data, I will examine this decreasing trend continues during the last decade (2012-). If so, I will explore which Arctic subregion has experienced the largest decrease in sea ice covers.

