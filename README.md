# MS-Decipher: a user-friendly proteome database search software with an emphasis on deciphering the spectra of O-linked glycopeptides 

[![Github all releases](https://img.shields.io/github/downloads/DICP-1809/MS-Decipher/total.svg)](https://github.com/DICP-1809/MS-Decipher/releases/)
[![GitHub version](https://img.shields.io/github/v/release/DICP-1809/MS-Decipher.svg)](https://github.com/DICP-1809/MS-Decipher/releases/tag/v1.0.0)

MS-Decipher is a user-friendly proteome database search software, with good performance comparing to traditional and latest database search tools. It supports two search modes: peptide and O-glycopeptide. Specially, the [O-Search](https://pubs.acs.org/doi/10.1021/acs.analchem.8b04184) strategy, which was developed by us before, is utilized to proceed the O-glycopeptide search. MS-Decipher also provides useful tools for the visualization of PSMs in the result and the generation of the scorer files.

MS-Decipher is written in the cross-platform Java programming language, with a GUI written in JavaFX. It has been packaged as an application, and put in a folder with other necessary configuration files and a java runtime environment (jre 11). Instructions on software installation and operation, common problems and other issues could be found in the documentations. 

## Download MS-Decipher
It is recommended to use MS-Decipher of the latest version, which could be downloaded [here](https://github.com/DICP-1809/MS-Decipher/releases), where previous version can also be acquired. The user guide is also included.

## Apply License for MS-Decipher
A license code is needed for the first time running MS-Decipher. User can fill in the chart, copy the information and sent it to glyco_decipher@163.com to apply for license.

![image](https://user-images.githubusercontent.com/84326485/160044627-a955b0c6-141c-43df-84d1-ef24ae8e1e12.png)         ![image](https://user-images.githubusercontent.com/84326485/160045091-12582d7c-8961-49d3-b145-517b555fb169.png)

## Cite
Jiawei Mao, He Zhu, Luyao Liu, Zheng Fang, Mingming Dong, Hongqiang Qin, Mingliang Ye, MS-Decipher: a user-friendly proteome database search software with an emphasis on deciphering the spectra of O-linked glycopeptides, Bioinformatics, Volume 38, Issue 7, 1 April 2022, Pages 1911–1919, https://doi.org/10.1093/bioinformatics/btac014

## Contact Us
### Group Leader: 
Mingliang Ye

email: mingliang@dicp.ac.cn
### Developer: 
Jiawei Mao

email: Mchem0077@163.com

He Zhu

email: hzhu@dicp.ac.cn

## Exception Handling
Log files, including information and errors, will be output when the software is running. If errors are encountered, users can check the error.log or ms_decipher.log file in the ‘logs’ folder to search for reasons, submit issues on https://github.com/DICP-1809/MS-Decipher or send email to glyco_decipher@163.com.

## Other software
For other software developed by the Mingliang Ye's Lab, please see https://github.com/DICP-1809.

## Run MS-Decipher
Users can run MS-Decipher on windows system by clicking the MS-Decipher.exe file, which can be obtained by unzipping the compressed .rar file. A graphical user interface will be shown for latter operation.

![image](https://user-images.githubusercontent.com/84326485/160044832-ff64307a-8977-4bb4-9b3d-6aa3506c9829.png)

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
