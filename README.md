# GEE_Python

This project is for using Google Earth Engine(GEE) with Python3 language.
I follow the suggestion from GEE, using **Google Colab** in the project.
Here are the introduction of each function in the project：

## 1. GEEtoXarray
This function is used to transfer GEE satellite image into Xarray's **DataArray** file format. 
The time-seires images of ROI will be stored in a 4-D DataArray. The output file could be further saved as **netCDF4** file.
