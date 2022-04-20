# Peak-alignment in LC/MS
## Introduction
這套軟體是一個基於LC/MS數據分析方法,我們會先經過peak detection 之後再將得到的峰值列表輸入到我們的程式中,讓峰值列表進行校正
## How to use
要使用之前,需準備每個峰值列表txt檔,放入同一資料夾讓程式讀取資料,接著我們會依需執行下列每個步驟
### Step 1. Setting all the parameters
我們必須先使用data.yml輸入各項參數,參數如下
#### Yml file parameters
|Name|Default Values|Comments|
|----|:-------------:|--------|
|input|D:\data|the location of txt file(**data為許多txt檔的資料夾**)|
|output|D:\tmp\output.txt|
|mztol|0.5|the value of M/Z tolerances|
|rttol|30.0|the value of retention time torlerances|
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
### Step 2.Using peak_alignment jar and  yml file
接著輸入下列的指令,讓程式執行
#### Commands
> java -jar peak_alignment  
> eg.,-jar "C:\Users\edwardkuo\Desktop\peak_alignment_jar\peak_alignment.jar"
### Output file
Peak alignment 會輸出一個表,這個表是校正過後的峰值列表
