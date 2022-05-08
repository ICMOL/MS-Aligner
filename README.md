# Peak-alignment and normalization tool with internal standard in LC/MS
## Introduction
這套軟體是一個基於LC/MS數據分析方法,我們會先經過peak detection 之後再將得到的峰值列表輸入到我們的程式中,讓峰值列表進行校正
## How to use
要使用之前,需準備每個峰值列表txt檔,放入同一資料夾讓程式讀取資料,接著我們會依需執行下列每個步驟
### Step 1. Setting all the parameters
我們必須先使用data.yml輸入各項參數,參數如下
#### Yml or txt file parameters
首先,我們用冒號與空白去做區隔,每打完一個參數就直接換行,
> ex., input: D:\data

參數如下
|Name|Default Values|Comments|
|----|:-------------:|--------|
|input|D:\data|the location of txt file(**data為許多txt檔的資料夾**)|
|output|D:\tmp\output.txt|the location of output file|
|mztol|0.5|the value of M/Z tolerances|
|rttol|30.0|the value of retention time torlerances(seconds)|
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
|normalization|1|是否需要normalization 1為是 0為否|
|normalizedmethod|0|normalization方法 0為不使用,1為把內標相加,2為內標平均,3為內標中位數 4為將每個intensity與相近的內標相除|
|normalized1_output_file_location|D:\tmp\normalization1.txt|經過第一次normalization|
|normalized2_output_file_location|D:\tmp\normalization2.txt|經過第二次normalization (take log2 and move to median)|
|internal|D:\tmp\internal.txt|內標值,內標格式格式會在下面附|
|separate|0| 0為不需要幫資料的質量控制樣本與其他樣本分離 1為需要|
|QC_new|D:\tmp\newQC.txt|QC樣本輸出路徑|
|sample_new|D:\tmp\sample.txt|其他樣本輸出路徑|
#### 內標格式
使用tab分開
|mz|rt|
|:----:|:-------------:|
|100|2.5|
|200|3.3|
### Step 2.Using peak_alignment jar and  yml file
接著輸入下列的指令,讓程式執行
#### Commands
> java -jar peak_alignment  parameter path
> eg.,java -jar D:\peak_alignment.jar D:\path.yml
### Output file
Peak alignment 會輸出一個表,這個表是校正過後的峰值列表和輸出normalization後的表
