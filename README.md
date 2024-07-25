# FSD
Code from MODIS FSD analysis

- see zenodo for results https://zenodo.org/records/11553700
- see https://github.com/WilhelmusLab/Segmentation_EB for algorithm

### sample_analysis.ipynb
FSD analysis:
- used this package to fit a powerlaw to the data: https://pypi.org/project/powerlaw/, article here: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0085777
- set xmin value based on minimum detectable floe size by algorithm (4.625 km^2, so set xmin=5)
- set xmax value based on histogram of the floe areas
- evolution, cloud analysis, relationship with sea ice concentration, etc.
