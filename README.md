# NPS_EML_Template
This repo contains a template and instructions for using EMLassemblyline to generate EML metadata for NPS data packages. It is expected that the product of EMLassemblyline will require additional editing, which must be accomplished using the [R/EMLeditor](https://github.com/nationalparkservice/EMLeditor) package.

This is an early version of this template. Please request enhancements and bug fixes through [Issues](https://github.com/nationalparkservice/NPS_EML_Template/issues).

For a comprehensive guide to generating EML via EMLassemblyline, please consult the accompanying [EML Template github website - DEV VERSION UPDATE LINK!](https://roblbaker.github.io/NPS_EML_Template/).

# Quickstart:

### Prior to generating EML you will need the following:

1) Data: A set of fully QA/QC'd data files in .csv format. If these are exported from a database, you may want to think strategically about what those files look like and how they will be accessed and utilized by future users of the data package (including, potentially, yourself!). These files must be encoded in UTF-8 format (if aren't sure whether your .csvs are in UTF-8 you can convert them by opening the .csv in Excel, you can choose to File > Save As and then select "CSV UTF-8 (Comma delimited) (*.csv)").

2) Software: R (and probably Rstudio) installed on your computer. These are both available in Software Center. See the [R Advisory Group's website](https://doimspp.sharepoint.com/sites/nps-nrss-imdiv/SitePages/R-Adv.aspx) for more information. You will also need to install the R package EMLassemblyline as well as some other packages from CRAN:

```r
>install.packages(c("EMLassemblyline", "lubridate", "tidyverse")
```

3) Internet access: A strong internet connection, particularly if you have taxonomic information as EMLassemblyline will use scientific names to populate taxonomic coverage fields from Kingdom down to species (and beyond).

4) Access to MS excel or other spreadsheet type program (this will really help editing tab-delimited files)

5) Access to notepad or other text editor (NOT MS Word) for writing abstracts, etc. while avoiding non-UTF8 encoded characters.

### Download the template (and associated folders/files):
This is where the download link will go

### Example EML creation:
Note that there are only two data files for the example package and they are both in the Example_files folder. For your EML document you need only supply data files; the other files will be generated during EML creation. The example data files are:
1) qry_Export_AA_Points.csv
2) qry_Export_AA_VegetationDetail.csv

Take a look at the other example files in the Example_files folder. All of the files generated by EMLassemblyline via the [EML_creation_template.R Script](./EML_creation_template.R) are there. To generate EML all you need to do is supply the .csv datafiles and use the EML_creation_template.R script - all the other files will be generated by the Template (and subsequently edited prior to making the EML document).

  Note that some of these files will be best edited in a text editor (e.g. abstract.txt).

  Some files are tab-separated and are best edited in a spreadsheet application such as excel (e.g. personnel.txt).

  Some files likely will not need to be edited at all! (e.g. taxonomic_coverage.txt)

### Generate your EML:
1) Download and edit the [EML_creation_template.R](./EML_creation_template.R) script as necessary and run each line or set of code (except the `r make_eml` function). This script can function as a stand-alone document. You do not need to download the entire repository (although if you want to you can do so as a .zip using [this link](https://github.com/nationalparkservice/NPS_EML_Template/zipball/master).
2) Edit the auto-generated .txt files using a text editor or spreadsheet application as necessary.
3) Run the `r make_eml` function (this could take a little while - particularly if you have a lot of taxonomic data).
4) Be sure to read and address any Issues or Warnings after running the `r make_eml` function

### Next steps:
The example EML file [EVER_AA_metadata.xml](Example_files/EVER_AA_metadata.xml) as well as the EML you have created are not the final step in NPS EML creation. At this point you have filled in much of the important scientific information in the metadata. However, to fully utilize DataStore's new capabilities and to make sure your data are easily discoverable and reusable, you still need to edit the EML file to provide NPS-specific information (e.g. publisher, unit connections, DOIs, etc). Currently, the only tool available is [R/EMLeditor](https://github.com/nationalparkservice/EMLeditor). Manually editing your metadata by hand is not recommended.

### For additional documentation please see:
1) The NPS guidelines for creating EML using EMLassemblyline on github
2) The original [EDI guidelines](https://ediorg.github.io/EMLassemblyline/articles/edit_tmplts.html) for creating EML


