# FSD
Code and results from MODIS FSD analysis

### df_all_withloc.csv
Segmentation Output:

- Output from the Ice Floe Tracker Image Segmentation routine is a csv with columns: 'index', 'label', 'area', 'centroid-0', 'centroid-1','axis_major_length', 'axis_minor_length', 'orientation', 'perimeter','intensity_mean', 'doy', 'year', 'perim_km', 'area_km', 'circ', 'lon_ps', 'lat_ps', 'lon', 'lat'.
- self explanatory except for maybe:
- centroid-0, centroid-1 are the xy pixel locations of the centroids of the floes
- the intensity mean is the average pixel value in the red channel of all pixels within the floe
- I calculate area_km (area in square km), perimeter_km (perimeter in km) and circ (circularity: (4pi * area_km)/(perim_km^2)).
- I add lat and lon locations corresponding to the centroids with knowledge of the location of the images processed (column names: lon,lat,lon_ps,lat_ps, in epsg 4326 and epsg 3413)

### sample_analysis.ipynb
FSD analysis:
- used this package to fit a powerlaw to the data: https://pypi.org/project/powerlaw/, article here: https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0085777
- set xmin value based on minimum detectable floe size by algorithm (4.625 km^2, so set xmin=5)
- set xmax value based on histogram of the floe areas
