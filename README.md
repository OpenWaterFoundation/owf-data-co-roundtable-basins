# owf-data-co-roundtable-basins #

This repository contains the [Open Water Foundation (OWF)](http://openwaterfoundation.org) dataset for Colorado Interbasin Compact Committee (IBCC) basins.
The IBCC was established by the Colorado Water for the 21st Century Act to facilitate conversations among Colorado's river basins and to address statewide water issues.  
Colorado is divided into eight major river basins, with the Denver metropolitan area designated as its own basin, separate from the South Platte Basin.
Each basin has its own roundtable to facilitate discussions on water management issues.
This is a foundational dataset that in the future will provide unique identifiers and other data for basins.
The identifiers will be used to link other datasets, such as water providers and municipalities within basins.
OWF has created and is maintaining this dataset to facilitate work on various data analysis and visualization projects in Colorado.

## Repository Contents ##

The repository contains the following:

```text
analysis/                         		TSTool software command files to process data into useful forms.
data-orig/					Folder containing original data files downloaded from agency websites.
  Colorado-IBCC-Basins-WGS84.geojson			Exported spatial data file from the Colorado Water Conservation Board Data Viewer's IBCC Basin layer, converted to WGS 84.
data/                           		Folder containing data files.
  Colorado-Roundtable-Basins.xlsx     		Simple Excel file containing core data.
  Colorado-Roundtable-Basins.csv      		The Excel file contents from the IBCCBasin worksheet converted to a csv file, useful for automated processing.
doc/
  ?                             		Additional documentation for the dataset.
.gitattributes                  		Git configuration file indicate repository configuration, in particular handling
												of line-ending and binary files.
.gitignore                      		Git configuration file to ignore files that should not be committed to the repository.
README.md                     		Explanation of repository contents, data files and sources and TSTool command files used to process the core data into other products.
```

### Colorado-Roundtable-Basins.xlsx Contents ###

The core Excel workbook that serves as the master data contains the following data columns within the **IBCCBasin** worksheet.

* **IBCCBasinName** -- name of the IBCC basin.  Most of the names are self-explanatory; however it should be understood that the Yampa Basin includes the Yampa, Green and White rivers, while the Southwest Basin includes the San Juan, Dolores and San Miguel rivers
* **CWCB_URL** -- [Colorado Water Conservation Board (CWCB)'s](http://cwcb.state.co.us/water-management/basin-roundtables/Pages/main.aspx) website URL that contains information about the basin
* **Roundtable_URL** -- the basin roundtable's website URL
* **Roundtable_URL_Flag** -- data status of Roundtable URLs; see more detail below
* **Comment** -- any other information about the basin

Descriptions of data columns are also provided in the **Notes** worksheet within the workbook.  This worksheet also details how the original data were downloaded and where to find those files.

#### Data Flags ####
Data columns with the word "Flag" added to the column name are an indication of data status as it relates to missing data.  The following conventions are used:
* G = is a known/good value.  
* g = is an estimated (but good) value.  The associated cell is also highlighted in yellow.
* N = is not applicable and a blank cell is expected.
* M = is known to be missing in original source and therefore a blank cell indicates that a value cannot be provided.
* m = is estimated to be missing.  The associated cell is also highlighted in gray.
* z = is unable to be confirmed.  A value is possible but cannot be confirmed one way or the other.  The associated cell is also highlighted in orange.
* x = OWF has not made an attempt to populate the cell at this time.  The value is missing because OWF has not attempted to find the value.  The associated cell is also highlighted in black.

* Note that colors are visible only in xlsx files and not csv files.*

Other worksheets within the workbook contain the following:

* **ChangeLog** worksheet indicates any changes made to the dataset, the date they occurred and who made the changes.

* **Metadata_IBCCBasin** worksheet serves as the metadata for data columns in the **IBCCBasin** worksheet.

### Colorado-Roundtable-Basins.csv Contents ###

This file is the **IBCCBasin** worksheet saved in csv format.

## Attribution ##

The data sources for this dataset are listed below.

* The [Colorado Water Conservation Board (CWCB)'s](http://cwcb.state.co.us/water-management/basin-roundtables/Pages/main.aspx) website contains information about the basin roundtables, such as dates for roundtable basin meetings, meeting minutes and links to reports and documents.
* [Colorado's Water Plan](https://www.colorado.gov/pacific/cowaterplan/basins) website also provides some information about each basin and provides links to basin roundtable websites, if applicable.  The website also provides links to Basin Implementation Plans.
* IBCC basin boundaries were found by accessing the Colorado Water Conservation Board's Data Viewer (https://www.coloradodnr.info/h5v/Index.html?viewer=cwcbviewer).  The "IBCC Basin" layer was downloaded and opened in QGIS, converted to WGS 84 (EPSG:4326) and saved in GeoJSON format.

## How to Use the Data ##

The Colorado Roundtable Basins dataset provides a list of IBCC basins.  In the future, there may be unique identifiers for each basin and this dataset will allow cross-referencing the identifiers
so that other datasets can be joined.  For example, the [Colorado Municipalities dataset](https://github.com/OpenWaterFoundation/owf-data-co-municipalities) contains basin names and can be used to link additional data.

The Excel or csv files can be used as tabular datasets as is, to create filtered lists or to link to other datasets.  Data-processing software such as TSTool can be used to link this dataset to other datasets.  Datasets can be used within GIS software to create maps.

The format and contents of the dataset will change over time.  It is recommended to save a copy of the dataset for local processing or to fix the version in time.

## Disclaimer ##

OWF has created a complete statewide dataset of roundtable basins.  OWF will attempt to fill data gaps as the dataset is used for analysis and funding allows for more data review.  OWF provides no guarantee as to the accuracy of the data.  **Use this dataset at your own risk.**  OWF welcomes feedback to improve the dataset.

## License ##

The license is being determined.  All the data are public so there are not really any restrictions on use.

## Contributing ##

The Open Water Foundation is adding value by cross-referencing datasets.
If you use the dataset and have comments, please contact the maintainers and/or use the GitHub issues to provide feedback.

## Maintainers ##

Kristin Swaim (@kswaim, kristin.swaim@openwaterfoundation.org) is the primary maintainer at the Open Water Foundation.

Steve Malers (@smalers, steve.malers@openwaterfoundation.org) is the secondary contact.

## Contributors ##

None yet, other than OWF staff.
