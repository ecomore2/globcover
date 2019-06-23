
<!-- README.md is generated from README.Rmd. Please edit that file -->

# GlobCover data

<!-- badges: start -->

<!-- badges: end -->

[GlobCover](http://due.esrin.esa.int/page_globcover.php) from
[ESA](https://www.esa.int/ESA) proposes global raster file (300-m
resolution) of land cover for 2005 and 2009. After having been croped to
the province of Vientiane prefecture (see [cleaning
pipeline](https://ecomore2.github.io/globcover/make_data.html)), the
`.GTiff` files are available
    here:

  - [GlobCover2005\_V2.2.tif](https://www.dropbox.com/s/gp790fng3awwb7t/Globcover2005_V2.2.tif?raw=1)
    (37
    Ko)
  - [GlobCover2009\_V2.3.tif](https://www.dropbox.com/s/d2fdtq8jofs38tf/Globcover2009_V2.3.tif?raw=1)
    (38 Ko)

The files can be downloaded directly from R as so:

``` r
library(raster)
tmp <- tempfile(fileext = ".tif")
download.file("https://www.dropbox.com/s/gp790fng3awwb7t/Globcover2005_V2.2.tif?raw=1", tmp)
Globcover2005_V2.2 <- raster(tmp)
download.file("https://www.dropbox.com/s/d2fdtq8jofs38tf/Globcover2009_V2.3.tif?raw=1", tmp)
Globcover2009_V2.3 <- raster(tmp)
```

The legend of these raster files are:

    #> # A tibble: 23 x 2
    #>    Value Label                                                                                                                         
    #>    <dbl> <chr>                                                                                                                         
    #>  1    11 Post-flooding or irrigated croplands (or aquatic)                                                                             
    #>  2    14 Rainfed croplands                                                                                                             
    #>  3    20 Mosaic cropland (50-70%) / vegetation (grassland/shrubland/forest) (20-50%)                                                   
    #>  4    30 Mosaic vegetation (grassland/shrubland/forest) (50-70%) / cropland (20-50%)                                                   
    #>  5    40 Closed to open (>15%) broadleaved evergreen or semi-deciduous forest (>5m)                                                    
    #>  6    50 Closed (>40%) broadleaved deciduous forest (>5m)                                                                              
    #>  7    60 Open (15-40%) broadleaved deciduous forest/woodland (>5m)                                                                     
    #>  8    70 Closed (>40%) needleleaved evergreen forest (>5m)                                                                             
    #>  9    90 Open (15-40%) needleleaved deciduous or evergreen forest (>5m)                                                                
    #> 10   100 Closed to open (>15%) mixed broadleaved and needleleaved forest (>5m)                                                         
    #> 11   110 Mosaic forest or shrubland (50-70%) / grassland (20-50%)                                                                      
    #> 12   120 Mosaic grassland (50-70%) / forest or shrubland (20-50%)                                                                      
    #> 13   130 Closed to open (>15%) (broadleaved or needleleaved, evergreen or deciduous) shrubland (<5m)                                   
    #> 14   140 Closed to open (>15%) herbaceous vegetation (grassland, savannas or lichens/mosses)                                           
    #> 15   150 Sparse (<15%) vegetation                                                                                                      
    #> 16   160 Closed to open (>15%) broadleaved forest regularly flooded (semi-permanently or temporarily) - Fresh or brackish water        
    #> 17   170 Closed (>40%) broadleaved forest or shrubland permanently flooded - Saline or brackish water                                  
    #> 18   180 Closed to open (>15%) grassland or woody vegetation on regularly flooded or waterlogged soil - Fresh, brackish or saline water
    #> 19   190 Artificial surfaces and associated areas (Urban areas >50%)                                                                   
    #> 20   200 Bare areas                                                                                                                    
    #> 21   210 Water bodies                                                                                                                  
    #> 22   220 Permanent snow and ice                                                                                                        
    #> 23   230 No data (burnt areas, clouds,…)
