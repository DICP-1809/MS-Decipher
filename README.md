# MS-Decipher: a user-friendly proteome database search software with an emphasis on deciphering the spectra of O-linked glycopeptides 

[![Github all releases](https://img.shields.io/github/downloads/DICP-1809/MS-Decipher/total.svg)](https://github.com/DICP-1809/MS-Decipher/releases/)
[![GitHub version](https://img.shields.io/github/v/release/DICP-1809/MS-Decipher.svg)](https://github.com/DICP-1809/MS-Decipher/releases/tag/v1.0.0)

MS-Decipher is a user-friendly proteome database search software, with good performance comparing to traditional and latest database search tools. It supports two search modes: peptide and O-glycopeptide. Specially, the [O-Search](https://pubs.acs.org/doi/10.1021/acs.analchem.8b04184) strategy, which was developed by us before, is utilized to proceed the O-glycopeptide search. MS-Decipher also provides useful tools for the visualization of PSMs in the result and the generation of the scorer files.

MS-Decipher is written in the cross-platform Java programming language, with a GUI written in JavaFX. It has been packaged as an application, and put in a folder with other necessary configuration files and a java runtime environment (jre 11). Instructions on software installation and operation, common problems and other issues could be found in the documentations. 

## Cite
Jiawei Mao, He Zhu, Luyao Liu, Zheng Fang, Mingming Dong, Hongqiang Qin, Mingliang Ye, MS-Decipher: a user-friendly proteome database search software with an emphasis on deciphering the spectra of O-linked glycopeptides, Bioinformatics, 2022;, btac014, https://doi.org/10.1093/bioinformatics/btac014

## Download MS-Decipher
It is recommended to use MS-Decipher of the latest version, which could be downloaded [here](https://github.com/DICP-1809/MS-Decipher/releases), where previous version can also be acquired. The user guide is also included.

## Other software
For other software developed by the Mingliang Ye's Lab, please see https://github.com/DICP-1809.

## Run MS-Decipher
Users can run MS-Decipher on windows system by clicking the MS-Decipher.exe file, which can be obtained by unzipping the compressed .rar file. A graphical user interface will be shown for latter operation.

![image](https://user-images.githubusercontent.com/83257455/116176810-5bd1f300-a745-11eb-9ab8-c4d89967bf58.png)

## System Requirements

Environment:
  <br>
* Java Runtime Environment or Java Development Kit with 11 or higher, which could be downloaded [here](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

## Basic Usage

* Run a Search Task
  <br>
The first panel of MS-Decipher is used to process search tasks. By clicking on the icons at the right side and below of ‘Parameter File’, parameter files and MS Data files could be added. Then after selecting the maximum threads allocating to the software from the text field in the bottom of the panel, the search task will be started by clicking on the ‘start’ button, which is labeled in green arrows.

* Report Search Results
  <br>
Validated results could be generated from the second panel. Paths of raw result files and output file can be selected through the buttons at the top left and bottom of the panel. Thresholds and other options, including whether to use percolator, FDR, score threshold, etc., could be modified on the right side. The report task is started similarly as the previous panel.

* Edit Parameters
  <br>
Parameter files could be created, modified and saved in the third panel. Users is able to set plenty of parameters here. The detailed description of params are listed in the instruction file in each release.

* View PSMs in Results
  <br>
We provide tools for viewing the results obtained from MS-Decipher. By choosing the ‘PSM Viewer’ in the ‘Toolbox’ panel, an additional window will pop up. Result files, together with corresponding MS data files can be selected from the ‘File’ option. Then special result of PSM and the matched ions will be shown in the spectrum. Species, charges of ions, colors and other settings could be modified through ‘Settings’ in ‘Edit’ option.

* Generate Scorer File for Rank Score
  <br>
Since MS-Decipher adopts the rank score algorithm, which utilizes special scorer files to calculate scores for each match, we provide a scorer generator in the last panel. Result file and its corresponding parameter file and data file could be selected, and the generating task starts by clicking the start button.

* View Task Progress
  <br>
The task progress is displayed in the task progress view at the bottom of each panel in real time (except for the parameter editor).

## Supported File Formats
MS-Decipher supports several different formats of files in different steps:
<br>
* Database Search: 
  <br>
MS data file in the format of .mzML, .mzXML, .mgf, .pkl
  <br>
The .mzML and .mgf file can be generated from [Proteome Discoverer](https://www.thermofisher.com/order/catalog/product/OPTON-30945#/OPTON-30945) or [MSConvert](http://proteowizard.sourceforge.net/tools.shtml)
* Result Validation: 
  <br>
Raw result file in the format of .dat, .csv(from [Mascot](https://www.matrixscience.com/)), pepXML, .xlsx(from MS-Decipher) and .mzIdentML
  <br>

## Config the Path of Percolator
MS-Decipher adopts two ways of estimating false discovery rate (FDR): rank of PSMs based on scores, and employment of Percolator. [Percolator](https://github.com/percolator/percolator) uses a semi-supervised machine learning to discriminate correct from incorrect peptide-spectrum matches, and calculates accurate statistics such as q-value and posterior error probabilities. The releases of Percolator could be found [here](https://github.com/percolator/percolator/releases).
