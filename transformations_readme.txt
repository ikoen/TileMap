//export tfw 
listgeo -tfw -no_norm -proj4 p013r032_7t20001020_z18_nn10.tif


// assign tfw to tiff -- 
geotifcp -e /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/p013r032_7t20001020_z18_nn10.tfw bandscomposites/p013r032_7t20001020_z18_321.tif  bandscomposites/p013r032_7t20001020_z18_321.geo.tif
Clio:band_combinations iliaskoen$ gdalinfo  bandscomposites/p013r032_7t20001020_z18_321.geo.tif



//assign SRS to geotiff. 
gdal_translate -a_srs '+proj=utm +zone=18 +datum=WGS84 +units=m +no_defs' /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/p013r032_7t20001020_z18_321.geo.tif /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/p013r032_7t20001020_z18_321.geo1.tif


//export tiles 
python /Library/Frameworks/GDAL.framework/Versions/1.8/Programs/gdal2tiles.py /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/p013r032_7t20001020_z18_321.geo1.tif /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/Tiles



/////////////// test o

gdal_translate -a_srs p013r032_7t20001020_z18_nn10.tif  /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/p013r032_7t20001020_z18_321.tif  /Users/iliaskoen/works/DuKode/digitalGraphitti/dev/band_combinations/bandscomposites/p013r032_7t20001020_z18_321.gtif 



gdal_translate -of JPEG -co "WORLDFILE=YES" p013r032_7t20001020_z18_nn10.tif p013r032_7t20001020_z18_nn10.jpeg