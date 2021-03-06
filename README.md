<p align="left">
  <img src="/images/UTSA_Logo_Website_UTSA_Logo_Left Justified.png" height="80" title="hover text">
</p>

# Statistical Analysis of Sea Ice Extent in the Arctic Ocean using AMSR Passive Microwave Satellite Data
- ME 5013 (Spring 2021) Big data analysis in extreme environments
- Final project done by Younghyun Koo (younghyun.koo@utsa.edu): monitoring of Arctic sea ice concentration and extent using AMSR passive microwave (PMW) satellite data
- Last update: May 03 2021

## 1. Introduction
  Sea ice is an important indicator of recent global climate change. According to many previous studies, the extent and thickness of sea ice has been decreased continuously during last few decades. In particular, the Arctic sea ice has been decreased much faster than the Antarctic. In this project, I will examine the spatiotemporal variations of sea ice extent (SIE) over the Arctic by using spaceborne remote sensing data. Passive microwave (PMW) sensors have been actively used for monitoring of sea ice extent due to its advantages in data availability regardless of weather conditions or time. I will use one of the representative PMW sensors called AMSR (Advanced Microwave Scanning Radiometer) to characterize the spatiotemporal variations of Arctic sea ice extent from 2012 to present.
  
## 2. Data
The AMSR-E/AMSR-2 data are available via National Snow & Ice Data Center (NSIDC) website (https://nsidc.org/data/AU_SI25/versions/1). This product is available from July 2012, so about 3,200 files (~40 MB per each file, total ~128 GB) are available right now. These files contain 25-km resolution sea ice concentration (SIC) calculated by the NASA algorithm, and the Arctic data have 448 X 304 grid sizes. Due to the authorization issue for the access to the NASA Earthdata, I coulnd not access to this data directly via web link, but I downloaded all of the data by using Python code for the bulk downloads (see nsidc-download_AU_SI25.001_2021-04-27.py). After I read the Arctic sea ice concentration data, I saved this numpy array as .npy file (~1.6 GB).
- Google drive link to the saved numpy array file (.npy): https://drive.google.com/file/d/1APbeRfhyeKb67eErScoJgeB227UCcmvQ/view?usp=sharing).
- All mapping & statistical analysis works can be done with the numpy arrays (sic_con.npy, lat.npy, lon.npy).

## 2. Code capabilities
Jupyter notebook file named "SIC_northern.ipynb" performs the following functions:
### (1) Read AMSR sea ice concentration data (.h5 format)
- Read .h5 files as numpy arrays (size: (448, 304, 3175))
- Remove and interpolate invalid data

### (2) Mapping of sea ice concentration
- Draw yearly/monthly maps of Arctic sea ice concentration
<p align="left">
  <img src="/images/SIC_maps.png" width="800" title="hover text">
</p>

### (3) Temporal analysis of sea ice extent (SIE)
- Yearly/monthly trend of sea ice extent for the Arctic region and 11 sub-regions
- Fast Fourier transform (FFT) to understand period trend of SIE
<p align="left">
  <img src="/images/temporal_analysis.png" width="700" title="hover text">
</p>

<p align="left">
  <img src="/images/Arctic_subregions.png" width="700" title="hover text">
</p>

### (4) Dendrogram
- Draw and analyze dendrograms to figure out the hierarchical structure of SIE by region and time.
<p align="left">
  <img src="/images/Dendrograms.png" width="700" title="hover text">
</p>

### (5) Statistical moments (skewness and kurtosis)
- Draw and analyze skeness and kurtosis of SIE with various smooth size
<p align="left">
  <img src="/images/skewness_kurtosis.png" width="800" title="hover text">
</p>

### (5) Principal component analysis (PCA)
- Reduce dimensions of SIC data by using PCA components
<p align="left">
  <img src="/images/PCA.png" width="700" title="hover text">
</p>

## 3. Necessary Python packages
Following Python packages are required to run this notebook file successfully.
- h5py: read hdf files (https://pypi.org/project/h5py/)
- pandas: organize the data into dataframe by time and by region (https://pandas.pydata.org/)
- numpy: read hdf files and variables as numpy arrays (https://numpy.org/)
- matplotlib: plot and map the result (https://matplotlib.org/)
- astrodendro: plot and analyze dendrograms (https://dendrograms.readthedocs.io/en/stable/)
- scikit-learn: conduct PCA analysis and statistical moments (https://scikit-learn.org/stable/)

## 4. Hypothesis
According to many previous studies and papers, the Arctic sea ice extent has been decreased during last few decades. By using AMSR sea ice data, I will examine this decreasing trend continues during the last decade (2012-). If so, I will explore which Arctic subregion has experienced the largest decrease in sea ice covers.

### Basic hypothesis:
* Arctic sea ice extent has decreased/increased during the last decade.
* Each Arctic sub-region shows different changes in sea ice extent.
* The spatiotemporal distribution of Arctic sea ice has a distinctive hierarchical structure.


## 5. Expected results
- Temporal changes/trends of sea ice extent from 2013 to present (for the entire Arctic region and 11 subregions)
- Hierarchical characteristics Arctic sea ice and its spatiotemporal distributions (e.g. multi-year ice v. first-year ice)
- Characteristics of spatiotemporal distributions of Arctic sea ice extent derived from the statistical moments and PCA analysis
