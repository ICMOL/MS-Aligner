## **Introduction**
Liquid chromatography coupled with tandem mass spectrometry (LC-MS/MS) is a powerful analytical technique widely used for identifying and quantifying complex biomolecules, such as metabolites and proteins, in biological samples. In metabolomics quantification, alignment across different samples is essential. This step is critical for subsequent analyses, such as identifying biomarkers and conducting group difference analysis. The accuracy of alignment directly influences the comparability and reliability of the data, which in turn affects the precision of research conclusions and their practical applications. To address this, we developed MS-Aligner, a command-line tool implemented in Java and designed for peak alignment. After [MS-Picker](https://github.com/ICMOL/MS-Picker) performs peak detection for LC-MS/MS-based metabolomics data, MS-Aligner can efficiently process the output data by aligning both replicate samples and samples across different contents.



## **System Requirement**
* [Java SE Runtime Environment 8(or above)](https://www.oracle.com/tw/java/technologies/javase/javase8-archive-downloads.html) is required to be installed prior to use AutoMod.


## **How to use**
### **step 1. Download JAR file**
Download the latest MS-Aligner JAR file, and use the command line to execute the tool by specifying the YMAL file and analyzed files. 

### **step 2. Set up parameter**
1. The folder path for analyzed files (.txt).
2. The path to the YAML file storing the parameters.
   
      Open the 'param.yml' file and edit the paramters if necessary.
      | Name | Default Values | Comments |
    | :---          |     :---:      |        :---   |
    | mztol | 0.05  | m/z tolerance(unit : Da.). |
      |rttol |0.5|retention time tolerance(unit : min.)|
      |output|D:\data\\ | output folder path|
      |WindowSize|20|window size for LOWESS regressions|
      |MinChargeState|1|minimum charge state|
      |MaxChargeState|4|maximum charge state|
      |MinRTRange|0.0|minimum retention time (unit: minute)|
      |MaxRTRange|9999.0|	maximum retention time (unit: minute)|
      |MinMassRange|0.0|minimum mass|
      |MaxMassRange|9999.0|maximum mass|
      |MinSample|1|minimum number of samples|
      |Level|2|export the result in two levels, 1:sample level; 2: replicate level|

### **step 3. Execute the command**
As an example
required documents： 
1. YAML file："D:\param.yml"
2. analyzad files (folder path)："D:\analyzed files"
> java -jar MS-Aligner.jar "D:\param.yml" "D:\analyzed files"

### **step 4. Output**
1. peakList.tsv：A table with detected metabolite features in rows and samples in columns
2. metricList.tsv：A table containing nine metrics used to evaluate peak quality is extracted from each file produced by [MS-Picker](https://github.com/ICMOL/MS-Picker).
   This file allows you to view the distribution of each metric in [DeNox](https://github.com/ICMOL/source-DeNox).
