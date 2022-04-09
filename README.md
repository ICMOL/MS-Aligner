# peak-alignment
## Introduction

## How to use
要使用之前,需準備每個批次的txt檔,則我們會輸出align之後的列表
### Step 1. setting all the parameters
### yaml file Parameters
|Name|Default Values|Comments|
|----|:-------------:|--------|
|input|D:\data|the location of txt file(**data為許多txt檔的資料夾**)|
|output|D:\tmp\output.txt|
|mztol|0.5|the value of M/Z tolerances|
|rttol|30.0|
|MinChargeState|1|
|MaxChargeState|4|
|MinRTRange|0.0|
|MaxRTRange|9999.0|
|MinMassRange|0.0|
|MaxMassRange|9999.0|
|MinIsotopicRatio|0.0|
|MaxIsotopicRatio|1.0|
|SN|10.0|
|MinAbundance|0.0|
|MinSample|1|
### Step 2.
## Commands
> java -jar peak_alignment
> eg.,-jar "C:\Users\edwardkuo\Desktop\peak_alignment_jar\peak_alignment.jar"
