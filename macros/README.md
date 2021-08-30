# FreeCAD macros
List of FreeCAD macros:

| Macro name                       | Description                                                      |
|----------------------------------|------------------------------------------------------------------|
| ProjectExportBomAndDrawings      | Export *.FCStd model tech drawings to PDF files and bundles      |
| ProjectExportStl                 | Export *.FCStd model body to stl object (requires tech draw)     |

## ProjectExportBomAndDrawings.FCMacro
### Requirements
- PyPDF2 python package, can be installed with "\<FreeCAD_Dir\>python -m pip install PyPDF2"
- *.FCStd model with single or multiple bodies
- Tech Draw page(s) based on Ax_Landscape/Portait_ISO7200_Pep.svg template
- Tech Draw page(s) filled with attributes, Document Name (DN) required format "\<project_id\>-\<revision\>-\<part_number\>-\<sheet_number\>"

### Usage
1. Execute macro via menu bar > macro > macros... > double click "ProjectExportBomAndDrawings"
2. Select *.FCStd model source directory
3. Select drawing export directory
4. Confirm selected directories
5. Select export options
- "Export single sheets as PDF" will export every Tech Draw page as single *.pdf file
- "Export single parts as PDF bundle" will bundle every Tech Draw page, if PN is defined and occures multiple
6. Export will be executed

The export will create single files per Tech Draw page. If option "Export single sheets as PDF" is selected, these file will be deleted after creating the bundles.
Two files will be created by default:
- DrawingIndex.csv - Contains meta information from all Tech Draw sheets
- \<project_id\>-\<revision\>.pdf - Bundle of all single sheets

## ProjectExportStl.FCMacro
### Requirements
- *.FCStd model with single or multiple bodies
- Tech Draw page(s) based on Ax_Landscape/Portait_ISO7200_Pep.svg template
- Tech Draw page(s) filled with attributes, Document Name (DN) required format "\<project_id\>-\<revision\>-\<part_number\>-\<sheet_number\>"
### Usage
1. Execute macro via menu bar > macro > macros... > double click "ProjectExportStl"
2. Select *.FCStd model source directory
3. Select STL export directory
4. Confirm selected directories
5. Export will be executed

The export will create single files per model body.
Files will be formated like:
\<project_id\>-\<revision\>-\<part_number\>.stl

## Copyright
Robert Krahl 2020