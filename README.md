# DATA-ACQUISITION
A custom build python based web Scraper which helps in building datasets from Google Earth Engine
## Abstract <br />
Google Earth Engine Explorer (EE Explorer) is a lightweight geospatial image data viewer with access to a large set of global and regional datasets available in the Google Earth Engine Data Catalog. It allows for quick viewing of data with the ability to zoom and pan anywhere on Earth, adjust visualization settings, and layer data to inspect change over time.

Google Earth Engine public data archive includes more than forty years of historical imagery and scientific datasets, updated and expanded daily.It includes the most popular series of Raster series like Sentinel, Landsat, Modis. Google provies its own cloud platform to visualize and do computation on spatial data.Google provides several machine learning algorithms for use. Google Earth Engine platform is not very compatible with deep learning pipelines.

These huge data can be leveraged in building deep learnning models which handles use cases like semantic segmentation and object detection.I developed a tool which can fetch images and corresponding labeled images from Google Earth Engine and arrange it in way it is compatible with deep learning pipelines.



## Library used <br /> 
- **json**
- **geemap**
- **ee**
- **geopandas**
- **os** 
- **glob**
- **gdal** 
- **pandas** 
- **numpy** 
- **math**
- **shapely** 
- **folium**

## Methodology
Terms:
- Date-span--> - User is interested in between this date range
- Region span--> - User is interested in images bounded within this region only
- Cloud Cover percentage--> Given multiple images of same place and time use the image with least cloud cover percentage
- Shape file--> Geometrical file used to filter region of interest

We first use **GEEMAP** to aquire the required image. This image is subject to many filteration like **Date-span**,**Region span**,**Cloud Cover percentage** etc.Then we create a shape file which is rectangular in shape. The coordinates of this shape files covers a small area of interest of the image.We download the image covered by this shape file. Then we up date the coordinates of the shape file to download the next image. We do this continously to build a dateset out Google Earth Engne data catalogue
