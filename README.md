# Creating Raster MBTiles from GeoTiff

There are 3 ways to create raster MBTiles from GeoTiff
- TileMill
- Gdal2mbtiles
- Mapbox Studio

## TileMill
TileMill is a precursor to Mapbox Studio online. Though not in active development, it has shifted to an [open open source](http://openopensource.org/) contributor model.

Raw GeoTiff File
![tilemill1](img/tilemill_1.png)

GeoTiff Rendered Output Export from QGIS
![tilemill1](img/tilemill_2.png)

[Get TileMill here](https://tilemill-project.github.io/tilemill/)

### Alternative
- [Kosmtik](https://github.com/kosmtik/kosmtik)
- [TileOven](https://github.com/florianf/tileoven)

### gdal2mbtiles
Converts GDAL readable datasets into an MBTiles file

[Get gda2mbtiles here](https://github.com/ecometrica/gdal2mbtiles)

Anaconda Installation Instructions

```sh
conda create -n python2 python=2.7 anaconda
activate python2
conda install gdal
pip install gdal2mbtiles
# Verify Installation
gdal2mbtiles --help

gdal2mbtiles -v --min-resolution 4 --max-resolution 12 geoTiff_raw.tif geoTiff_raw.mbtiles
```

### gdal_translate
Use gdal_translate convert the geotiff to mbtiles

```sh
gdal_translate geoTiff_raw.tif output.mbtiles -of MBTILES
# OR
gdal_translate geoTiff_raw.tif -b mask out.tif
gdal_translate out.tif out.mbtiles -of MBTILES
```

### rio-mbtiles
A plugin for the Rasterio CLI that exports a raster dataset to the MBTiles (version 1.1) format. Features include automatic reprojection and parallel processing.
[Get rio-mbtiles here](https://github.com/mapbox/rio-mbtiles)


#### References
[Adding a color table to one band Tiff](https://gis.stackexchange.com/questions/104196/how-to-add-a-color-table-to-a-one-band-tiff-using-gdal)