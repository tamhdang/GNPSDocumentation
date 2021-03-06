## Tutorial Using MetaboScape and GNPS

In this tutorial you will be guided into running MetaboScape for the Feature Based Molecular Network (FBMN) workflow on GNPS to reproduce some findings of the Coffee project.

## Learning Objectives

1. Run MetaboScape feature detection on LC-MS/MS data, and receive a feature quantification table and a MS2 spectral file as an output. [See the tutorial here](../featurebasedmolecularnetworking.md).
2. Run GNPS and visualize output in Cytoscape.

## Experimental Setup

We will use a subset of the LC-MS/MS analysis from the Coffee project. 

*Sample description still needed?* 

MetaboScape will be used to detect features and output a feature quantification table (.csv format) and a MS2 spectral file (.mgf format). The feature quantification table contains the intensity values for every aligned peak accross the samples, while the MS2 spectral file contains a single MS2 representing each aligned peak.

## Data and Files Needed for the Tutorial

LC-MS/MS data and files can be found in the MassIVE dataset.

## MetaboScape Representative Output Files
These files are not needed for the tutorial but are provided here as reference files, or if you want to bypass the MetaboScape processing.

|     File Type    | Download Link          |
| ------------- |------------- |
| Feature quantification table (.csv format) | [Download](https://github.com/lfnothias/GNPSDocumentation/blob/master/docs/tutorials/AG_tutorial_files/MetaboScape-GNPS-Coffee_Tutorial_msmsonly_featuretable.csv) |
| MS2 spectral file (.mgf format) | [Download](https://github.com/lfnothias/GNPSDocumentation/blob/master/docs/tutorials/AG_tutorial_files/MetaboScape-GNPS-Coffee_Tutorial.mgf) |

## Required Software Installations

1. FTP Client (e.g. WinSCP, DO NOT USE FileZilla!) [See instructions here](http://proteomics.ucsd.edu/service/massive/documentation/submit-data/upload-data/).
2. MetaboScape, commercially available from Bruker. 
3. [Cytoscape](http://www.cytoscape.org/download.php) for network visualization.

## Run MetaboScape
Refer to the detailed step-by-step procedure to run Metaboscape [here](../featurebasedmolecularnetworking-with-metaboscape.md).

## Run GNPS

See the documentation to produce molecular network at GNPS [here](../featurebasedmolecularnetworking.md).

## Run Cytoscape for Visualization of Molecular Networks

1. Open Cytoscape 3.4 (or more recent version).
2. Install the Cytoscape App ChemViz2 and download it [here](http://apps.cytoscape.org/apps/chemviz2).
3. Import the molecular networking files downloaded from GNPS into Cytoscape.
 - Import the network topology. Go to *File/Import/Network/File* and select the *.pairsinfo* file in *networkedges_selfloop* folder.
 - Import the node information table. Go to *File/Import/Table/File* and select the .tsv file in *clusterinfosummarygroup_attributes_withIDs_withcomponentID* folder.
 - Import the MS/MS spectral library annotation table. Go to *File/Import/Table/File* and select the .tsv file in *result_specnets_DB folder*.
 - Import the bucket table (MS/MS only) exported from MetaboScape. Go to *File/Import/Table/File* and select the .csv file.
 
#### Molecular network topology import

![img](img/metaboscapeexportforgnps/Cyto3.PNG)
 
#### Node table import interface

![img](img/metaboscapeexportforgnps/Cyto6.PNG)
 
4. Configure the Cytoscape style.
 - For the *Label* properties. Select the column MOLECULAR_FORMULA and choose *Passthrough Mapping* as mapping type.
 - For the *Size* properties. Select the column SAMPLE and choose *Continuous Mapping* as mapping type.

#### Molecular network style configuration

![img](img/metaboscapeexportforgnps/Cyto7.PNG)
 
5. Visualize the bucket table as a pie chart diagram. Click on the *Def.* box for the *Image/Chart* properties.
 - Click on the *Charts* spreadsheet and select the group for visualization.
 - Click on the option *Charts/option* spreadsheet and select the color-code for each group.
 
#### Pie chart configuration (data in *Image/Chart* properties)

![img](img/metaboscapeexportforgnps/Cyto8.PNG)

#### Pie chart configuration (options in *Image/Chart* properties)

![img](img/metaboscapeexportforgnps/Cyto9.PNG)

6. Visualize the MS/MS spectral library annotations (make sure ChemViz2 is installed).
 - Select the nodes with MS/MS spectral library annotation (column *LibraryID* in the Cytoscape node table).
 - Right-click on the nodes and select */Apps/Cheminformatics/Show compounds table* or alternatively */Apps/Cheminformatics/Show structures for selected nodes* or */Apps/Cheminformatics/Paint structures for selected nodes*.
 
#### Molecular networks visualization with molecular formula annotation (node name)

![img](img/metaboscapeexportforgnps/Cyto10.PNG)

#### View of compounds structures for spectral library MS/MS annotation in the molecular network

![img](img/metaboscapeexportforgnps/Cyto12.PNG)

#### Molecular network with MS/MS spectral annotation

![img](img/metaboscapeexportforgnps/Cyto13.PNG)


For more information, see the documentation to perform visualization of the molecular networking on the data of the Coffee Project [here](../featurebasedmolecularnetworking-cytoscape.md).

