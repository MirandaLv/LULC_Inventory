# LULC Inventory


Building footprints will be classified as either commercial or residential to help identify developed areas within the NLDC that correspond to residential or commercial land use.

**The recommended method:**

Using the existing global level building footprint published by: https://www.nature.com/articles/s41597-024-03219-x#Tab2 and merge with the current NLCD to generate the output.

Steps: 

1. Download the building file from the paper, here is the direct link to download: https://disasters.geoplatform.gov/USA_Structures/. For more information about how this dataset is generated and the metadata attributes, refer to the paper: https://www.nature.com/articles/s41597-024-03219-x#Tab2
2. Extract buildings that fall into a county boundary, by overlaying the county boundary with the building footprint data. Be mind of the projection.
3. Download the county level landuse and land cover data from NLCD. Be mind of the projection, make sure that all the layers are in the same projection.
4. Take the York county for example, save the York county cropped NLCD data and the structure data into separate files. Run baseline_structure_inventory. 

 
    python baseline_structure_inventory.py -b ../data/structure_inventory/York/buildingfilename.shp -lulc ../data/lulc/York/lulcfile.tif -olr ../outputs/York/reclassifylulc(you can name it).tif  -obr ../outputs/York/buildingreclass(you can name it).tif -o ../outputs/York/final_pathfile(ThisIstheFinalfile).tif


