# Impact of Single Landsat Coverage on the Interpolation Process used to Generate OpenET Monthly ET Estimates

## Approach

The overall goal of this analysis is to test and compare how well the OpenET interpolation process is able to generate monthly ET totals from Landsat ET fractions estimates for time periods with single and dual Landsat coverage.

The "target" monthly ET values were generated by combining daily grass reference ET (ETo) from GRIDMET with daily crop coefficient "Kc" curves from ET-Demands to compute daily ET, and then aggregating tto the month.

The interpolated monthly ET values were generated using the same daily ETo as the target values, but the daily Kc was computed by interpolating from only the Kc values that would have been available on cloud free Landsat observation dates for that region.  

For location and crop, separate interpolations were made for each year in the Landsat archive.  The years were grouped depending on whether there was single Landsat coverage (1984-1998, 2012) or dual Landsat coverage (1999-2011, 2013-present).  Some years in the later time period were excluded in order to have a similar count between the two groups, and to avoid years with only partial dual coverage (1999, 2013).

## Files/Data

### ET Cells Metadata

The "et_cell_metadata.csv" file has the list of "ET Cell" locations that will be used for this analysis.  The ET cells listed in the file are a subset of the cells used to calibrated various ET-Demands runs for the Upper Colorado Basin, Klamath Basin, and Oregon.  Each of the ET cells listed has one or more crop coefficient (Kc) curve files in the "kc" folder.

### Kc

CSV files the crop coefficient (Kc) for each ET cell and crop are stored in the "kc" folder.  These files were provided by Chris and he said additional crop files could probably be provided if needed.

### ETo

CSV files of the bias corrected GRIDMET reference ET (ETo) for each ET cell centroid and year are stored in the "eto" folder.  These were generated using the download_eto_data.ipynb tool.  This tool would need to be rerun if additional ET cell locations were added to the metadata file.

### ETf

CSV files of the ET fraction (ETf) for each ET cell and year are stored in the "etf" folder.  These were generated using the eto download_eto_data.ipynb tool.
