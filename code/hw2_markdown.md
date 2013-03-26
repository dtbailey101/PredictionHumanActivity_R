Homework 2
====================

Preprocessing
-------------

### Load Data

```r
setwd("~/Users/SMW/Dropbox/Coursera/DA_012213/Homework/HW2/code")
##
## download.file('https://spark-public.s3.amazonaws.com/dataanalysis/samsungData.rda',
## '../data/samsungData.rda')
load("../data/samsungData.rda")
```


### Examine raw data

```r
names(samsungData)
```

```
##   [1] "tBodyAcc-mean()-X"                   
##   [2] "tBodyAcc-mean()-Y"                   
##   [3] "tBodyAcc-mean()-Z"                   
##   [4] "tBodyAcc-std()-X"                    
##   [5] "tBodyAcc-std()-Y"                    
##   [6] "tBodyAcc-std()-Z"                    
##   [7] "tBodyAcc-mad()-X"                    
##   [8] "tBodyAcc-mad()-Y"                    
##   [9] "tBodyAcc-mad()-Z"                    
##  [10] "tBodyAcc-max()-X"                    
##  [11] "tBodyAcc-max()-Y"                    
##  [12] "tBodyAcc-max()-Z"                    
##  [13] "tBodyAcc-min()-X"                    
##  [14] "tBodyAcc-min()-Y"                    
##  [15] "tBodyAcc-min()-Z"                    
##  [16] "tBodyAcc-sma()"                      
##  [17] "tBodyAcc-energy()-X"                 
##  [18] "tBodyAcc-energy()-Y"                 
##  [19] "tBodyAcc-energy()-Z"                 
##  [20] "tBodyAcc-iqr()-X"                    
##  [21] "tBodyAcc-iqr()-Y"                    
##  [22] "tBodyAcc-iqr()-Z"                    
##  [23] "tBodyAcc-entropy()-X"                
##  [24] "tBodyAcc-entropy()-Y"                
##  [25] "tBodyAcc-entropy()-Z"                
##  [26] "tBodyAcc-arCoeff()-X,1"              
##  [27] "tBodyAcc-arCoeff()-X,2"              
##  [28] "tBodyAcc-arCoeff()-X,3"              
##  [29] "tBodyAcc-arCoeff()-X,4"              
##  [30] "tBodyAcc-arCoeff()-Y,1"              
##  [31] "tBodyAcc-arCoeff()-Y,2"              
##  [32] "tBodyAcc-arCoeff()-Y,3"              
##  [33] "tBodyAcc-arCoeff()-Y,4"              
##  [34] "tBodyAcc-arCoeff()-Z,1"              
##  [35] "tBodyAcc-arCoeff()-Z,2"              
##  [36] "tBodyAcc-arCoeff()-Z,3"              
##  [37] "tBodyAcc-arCoeff()-Z,4"              
##  [38] "tBodyAcc-correlation()-X,Y"          
##  [39] "tBodyAcc-correlation()-X,Z"          
##  [40] "tBodyAcc-correlation()-Y,Z"          
##  [41] "tGravityAcc-mean()-X"                
##  [42] "tGravityAcc-mean()-Y"                
##  [43] "tGravityAcc-mean()-Z"                
##  [44] "tGravityAcc-std()-X"                 
##  [45] "tGravityAcc-std()-Y"                 
##  [46] "tGravityAcc-std()-Z"                 
##  [47] "tGravityAcc-mad()-X"                 
##  [48] "tGravityAcc-mad()-Y"                 
##  [49] "tGravityAcc-mad()-Z"                 
##  [50] "tGravityAcc-max()-X"                 
##  [51] "tGravityAcc-max()-Y"                 
##  [52] "tGravityAcc-max()-Z"                 
##  [53] "tGravityAcc-min()-X"                 
##  [54] "tGravityAcc-min()-Y"                 
##  [55] "tGravityAcc-min()-Z"                 
##  [56] "tGravityAcc-sma()"                   
##  [57] "tGravityAcc-energy()-X"              
##  [58] "tGravityAcc-energy()-Y"              
##  [59] "tGravityAcc-energy()-Z"              
##  [60] "tGravityAcc-iqr()-X"                 
##  [61] "tGravityAcc-iqr()-Y"                 
##  [62] "tGravityAcc-iqr()-Z"                 
##  [63] "tGravityAcc-entropy()-X"             
##  [64] "tGravityAcc-entropy()-Y"             
##  [65] "tGravityAcc-entropy()-Z"             
##  [66] "tGravityAcc-arCoeff()-X,1"           
##  [67] "tGravityAcc-arCoeff()-X,2"           
##  [68] "tGravityAcc-arCoeff()-X,3"           
##  [69] "tGravityAcc-arCoeff()-X,4"           
##  [70] "tGravityAcc-arCoeff()-Y,1"           
##  [71] "tGravityAcc-arCoeff()-Y,2"           
##  [72] "tGravityAcc-arCoeff()-Y,3"           
##  [73] "tGravityAcc-arCoeff()-Y,4"           
##  [74] "tGravityAcc-arCoeff()-Z,1"           
##  [75] "tGravityAcc-arCoeff()-Z,2"           
##  [76] "tGravityAcc-arCoeff()-Z,3"           
##  [77] "tGravityAcc-arCoeff()-Z,4"           
##  [78] "tGravityAcc-correlation()-X,Y"       
##  [79] "tGravityAcc-correlation()-X,Z"       
##  [80] "tGravityAcc-correlation()-Y,Z"       
##  [81] "tBodyAccJerk-mean()-X"               
##  [82] "tBodyAccJerk-mean()-Y"               
##  [83] "tBodyAccJerk-mean()-Z"               
##  [84] "tBodyAccJerk-std()-X"                
##  [85] "tBodyAccJerk-std()-Y"                
##  [86] "tBodyAccJerk-std()-Z"                
##  [87] "tBodyAccJerk-mad()-X"                
##  [88] "tBodyAccJerk-mad()-Y"                
##  [89] "tBodyAccJerk-mad()-Z"                
##  [90] "tBodyAccJerk-max()-X"                
##  [91] "tBodyAccJerk-max()-Y"                
##  [92] "tBodyAccJerk-max()-Z"                
##  [93] "tBodyAccJerk-min()-X"                
##  [94] "tBodyAccJerk-min()-Y"                
##  [95] "tBodyAccJerk-min()-Z"                
##  [96] "tBodyAccJerk-sma()"                  
##  [97] "tBodyAccJerk-energy()-X"             
##  [98] "tBodyAccJerk-energy()-Y"             
##  [99] "tBodyAccJerk-energy()-Z"             
## [100] "tBodyAccJerk-iqr()-X"                
## [101] "tBodyAccJerk-iqr()-Y"                
## [102] "tBodyAccJerk-iqr()-Z"                
## [103] "tBodyAccJerk-entropy()-X"            
## [104] "tBodyAccJerk-entropy()-Y"            
## [105] "tBodyAccJerk-entropy()-Z"            
## [106] "tBodyAccJerk-arCoeff()-X,1"          
## [107] "tBodyAccJerk-arCoeff()-X,2"          
## [108] "tBodyAccJerk-arCoeff()-X,3"          
## [109] "tBodyAccJerk-arCoeff()-X,4"          
## [110] "tBodyAccJerk-arCoeff()-Y,1"          
## [111] "tBodyAccJerk-arCoeff()-Y,2"          
## [112] "tBodyAccJerk-arCoeff()-Y,3"          
## [113] "tBodyAccJerk-arCoeff()-Y,4"          
## [114] "tBodyAccJerk-arCoeff()-Z,1"          
## [115] "tBodyAccJerk-arCoeff()-Z,2"          
## [116] "tBodyAccJerk-arCoeff()-Z,3"          
## [117] "tBodyAccJerk-arCoeff()-Z,4"          
## [118] "tBodyAccJerk-correlation()-X,Y"      
## [119] "tBodyAccJerk-correlation()-X,Z"      
## [120] "tBodyAccJerk-correlation()-Y,Z"      
## [121] "tBodyGyro-mean()-X"                  
## [122] "tBodyGyro-mean()-Y"                  
## [123] "tBodyGyro-mean()-Z"                  
## [124] "tBodyGyro-std()-X"                   
## [125] "tBodyGyro-std()-Y"                   
## [126] "tBodyGyro-std()-Z"                   
## [127] "tBodyGyro-mad()-X"                   
## [128] "tBodyGyro-mad()-Y"                   
## [129] "tBodyGyro-mad()-Z"                   
## [130] "tBodyGyro-max()-X"                   
## [131] "tBodyGyro-max()-Y"                   
## [132] "tBodyGyro-max()-Z"                   
## [133] "tBodyGyro-min()-X"                   
## [134] "tBodyGyro-min()-Y"                   
## [135] "tBodyGyro-min()-Z"                   
## [136] "tBodyGyro-sma()"                     
## [137] "tBodyGyro-energy()-X"                
## [138] "tBodyGyro-energy()-Y"                
## [139] "tBodyGyro-energy()-Z"                
## [140] "tBodyGyro-iqr()-X"                   
## [141] "tBodyGyro-iqr()-Y"                   
## [142] "tBodyGyro-iqr()-Z"                   
## [143] "tBodyGyro-entropy()-X"               
## [144] "tBodyGyro-entropy()-Y"               
## [145] "tBodyGyro-entropy()-Z"               
## [146] "tBodyGyro-arCoeff()-X,1"             
## [147] "tBodyGyro-arCoeff()-X,2"             
## [148] "tBodyGyro-arCoeff()-X,3"             
## [149] "tBodyGyro-arCoeff()-X,4"             
## [150] "tBodyGyro-arCoeff()-Y,1"             
## [151] "tBodyGyro-arCoeff()-Y,2"             
## [152] "tBodyGyro-arCoeff()-Y,3"             
## [153] "tBodyGyro-arCoeff()-Y,4"             
## [154] "tBodyGyro-arCoeff()-Z,1"             
## [155] "tBodyGyro-arCoeff()-Z,2"             
## [156] "tBodyGyro-arCoeff()-Z,3"             
## [157] "tBodyGyro-arCoeff()-Z,4"             
## [158] "tBodyGyro-correlation()-X,Y"         
## [159] "tBodyGyro-correlation()-X,Z"         
## [160] "tBodyGyro-correlation()-Y,Z"         
## [161] "tBodyGyroJerk-mean()-X"              
## [162] "tBodyGyroJerk-mean()-Y"              
## [163] "tBodyGyroJerk-mean()-Z"              
## [164] "tBodyGyroJerk-std()-X"               
## [165] "tBodyGyroJerk-std()-Y"               
## [166] "tBodyGyroJerk-std()-Z"               
## [167] "tBodyGyroJerk-mad()-X"               
## [168] "tBodyGyroJerk-mad()-Y"               
## [169] "tBodyGyroJerk-mad()-Z"               
## [170] "tBodyGyroJerk-max()-X"               
## [171] "tBodyGyroJerk-max()-Y"               
## [172] "tBodyGyroJerk-max()-Z"               
## [173] "tBodyGyroJerk-min()-X"               
## [174] "tBodyGyroJerk-min()-Y"               
## [175] "tBodyGyroJerk-min()-Z"               
## [176] "tBodyGyroJerk-sma()"                 
## [177] "tBodyGyroJerk-energy()-X"            
## [178] "tBodyGyroJerk-energy()-Y"            
## [179] "tBodyGyroJerk-energy()-Z"            
## [180] "tBodyGyroJerk-iqr()-X"               
## [181] "tBodyGyroJerk-iqr()-Y"               
## [182] "tBodyGyroJerk-iqr()-Z"               
## [183] "tBodyGyroJerk-entropy()-X"           
## [184] "tBodyGyroJerk-entropy()-Y"           
## [185] "tBodyGyroJerk-entropy()-Z"           
## [186] "tBodyGyroJerk-arCoeff()-X,1"         
## [187] "tBodyGyroJerk-arCoeff()-X,2"         
## [188] "tBodyGyroJerk-arCoeff()-X,3"         
## [189] "tBodyGyroJerk-arCoeff()-X,4"         
## [190] "tBodyGyroJerk-arCoeff()-Y,1"         
## [191] "tBodyGyroJerk-arCoeff()-Y,2"         
## [192] "tBodyGyroJerk-arCoeff()-Y,3"         
## [193] "tBodyGyroJerk-arCoeff()-Y,4"         
## [194] "tBodyGyroJerk-arCoeff()-Z,1"         
## [195] "tBodyGyroJerk-arCoeff()-Z,2"         
## [196] "tBodyGyroJerk-arCoeff()-Z,3"         
## [197] "tBodyGyroJerk-arCoeff()-Z,4"         
## [198] "tBodyGyroJerk-correlation()-X,Y"     
## [199] "tBodyGyroJerk-correlation()-X,Z"     
## [200] "tBodyGyroJerk-correlation()-Y,Z"     
## [201] "tBodyAccMag-mean()"                  
## [202] "tBodyAccMag-std()"                   
## [203] "tBodyAccMag-mad()"                   
## [204] "tBodyAccMag-max()"                   
## [205] "tBodyAccMag-min()"                   
## [206] "tBodyAccMag-sma()"                   
## [207] "tBodyAccMag-energy()"                
## [208] "tBodyAccMag-iqr()"                   
## [209] "tBodyAccMag-entropy()"               
## [210] "tBodyAccMag-arCoeff()1"              
## [211] "tBodyAccMag-arCoeff()2"              
## [212] "tBodyAccMag-arCoeff()3"              
## [213] "tBodyAccMag-arCoeff()4"              
## [214] "tGravityAccMag-mean()"               
## [215] "tGravityAccMag-std()"                
## [216] "tGravityAccMag-mad()"                
## [217] "tGravityAccMag-max()"                
## [218] "tGravityAccMag-min()"                
## [219] "tGravityAccMag-sma()"                
## [220] "tGravityAccMag-energy()"             
## [221] "tGravityAccMag-iqr()"                
## [222] "tGravityAccMag-entropy()"            
## [223] "tGravityAccMag-arCoeff()1"           
## [224] "tGravityAccMag-arCoeff()2"           
## [225] "tGravityAccMag-arCoeff()3"           
## [226] "tGravityAccMag-arCoeff()4"           
## [227] "tBodyAccJerkMag-mean()"              
## [228] "tBodyAccJerkMag-std()"               
## [229] "tBodyAccJerkMag-mad()"               
## [230] "tBodyAccJerkMag-max()"               
## [231] "tBodyAccJerkMag-min()"               
## [232] "tBodyAccJerkMag-sma()"               
## [233] "tBodyAccJerkMag-energy()"            
## [234] "tBodyAccJerkMag-iqr()"               
## [235] "tBodyAccJerkMag-entropy()"           
## [236] "tBodyAccJerkMag-arCoeff()1"          
## [237] "tBodyAccJerkMag-arCoeff()2"          
## [238] "tBodyAccJerkMag-arCoeff()3"          
## [239] "tBodyAccJerkMag-arCoeff()4"          
## [240] "tBodyGyroMag-mean()"                 
## [241] "tBodyGyroMag-std()"                  
## [242] "tBodyGyroMag-mad()"                  
## [243] "tBodyGyroMag-max()"                  
## [244] "tBodyGyroMag-min()"                  
## [245] "tBodyGyroMag-sma()"                  
## [246] "tBodyGyroMag-energy()"               
## [247] "tBodyGyroMag-iqr()"                  
## [248] "tBodyGyroMag-entropy()"              
## [249] "tBodyGyroMag-arCoeff()1"             
## [250] "tBodyGyroMag-arCoeff()2"             
## [251] "tBodyGyroMag-arCoeff()3"             
## [252] "tBodyGyroMag-arCoeff()4"             
## [253] "tBodyGyroJerkMag-mean()"             
## [254] "tBodyGyroJerkMag-std()"              
## [255] "tBodyGyroJerkMag-mad()"              
## [256] "tBodyGyroJerkMag-max()"              
## [257] "tBodyGyroJerkMag-min()"              
## [258] "tBodyGyroJerkMag-sma()"              
## [259] "tBodyGyroJerkMag-energy()"           
## [260] "tBodyGyroJerkMag-iqr()"              
## [261] "tBodyGyroJerkMag-entropy()"          
## [262] "tBodyGyroJerkMag-arCoeff()1"         
## [263] "tBodyGyroJerkMag-arCoeff()2"         
## [264] "tBodyGyroJerkMag-arCoeff()3"         
## [265] "tBodyGyroJerkMag-arCoeff()4"         
## [266] "fBodyAcc-mean()-X"                   
## [267] "fBodyAcc-mean()-Y"                   
## [268] "fBodyAcc-mean()-Z"                   
## [269] "fBodyAcc-std()-X"                    
## [270] "fBodyAcc-std()-Y"                    
## [271] "fBodyAcc-std()-Z"                    
## [272] "fBodyAcc-mad()-X"                    
## [273] "fBodyAcc-mad()-Y"                    
## [274] "fBodyAcc-mad()-Z"                    
## [275] "fBodyAcc-max()-X"                    
## [276] "fBodyAcc-max()-Y"                    
## [277] "fBodyAcc-max()-Z"                    
## [278] "fBodyAcc-min()-X"                    
## [279] "fBodyAcc-min()-Y"                    
## [280] "fBodyAcc-min()-Z"                    
## [281] "fBodyAcc-sma()"                      
## [282] "fBodyAcc-energy()-X"                 
## [283] "fBodyAcc-energy()-Y"                 
## [284] "fBodyAcc-energy()-Z"                 
## [285] "fBodyAcc-iqr()-X"                    
## [286] "fBodyAcc-iqr()-Y"                    
## [287] "fBodyAcc-iqr()-Z"                    
## [288] "fBodyAcc-entropy()-X"                
## [289] "fBodyAcc-entropy()-Y"                
## [290] "fBodyAcc-entropy()-Z"                
## [291] "fBodyAcc-maxInds-X"                  
## [292] "fBodyAcc-maxInds-Y"                  
## [293] "fBodyAcc-maxInds-Z"                  
## [294] "fBodyAcc-meanFreq()-X"               
## [295] "fBodyAcc-meanFreq()-Y"               
## [296] "fBodyAcc-meanFreq()-Z"               
## [297] "fBodyAcc-skewness()-X"               
## [298] "fBodyAcc-kurtosis()-X"               
## [299] "fBodyAcc-skewness()-Y"               
## [300] "fBodyAcc-kurtosis()-Y"               
## [301] "fBodyAcc-skewness()-Z"               
## [302] "fBodyAcc-kurtosis()-Z"               
## [303] "fBodyAcc-bandsEnergy()-1,8"          
## [304] "fBodyAcc-bandsEnergy()-9,16"         
## [305] "fBodyAcc-bandsEnergy()-17,24"        
## [306] "fBodyAcc-bandsEnergy()-25,32"        
## [307] "fBodyAcc-bandsEnergy()-33,40"        
## [308] "fBodyAcc-bandsEnergy()-41,48"        
## [309] "fBodyAcc-bandsEnergy()-49,56"        
## [310] "fBodyAcc-bandsEnergy()-57,64"        
## [311] "fBodyAcc-bandsEnergy()-1,16"         
## [312] "fBodyAcc-bandsEnergy()-17,32"        
## [313] "fBodyAcc-bandsEnergy()-33,48"        
## [314] "fBodyAcc-bandsEnergy()-49,64"        
## [315] "fBodyAcc-bandsEnergy()-1,24"         
## [316] "fBodyAcc-bandsEnergy()-25,48"        
## [317] "fBodyAcc-bandsEnergy()-1,8"          
## [318] "fBodyAcc-bandsEnergy()-9,16"         
## [319] "fBodyAcc-bandsEnergy()-17,24"        
## [320] "fBodyAcc-bandsEnergy()-25,32"        
## [321] "fBodyAcc-bandsEnergy()-33,40"        
## [322] "fBodyAcc-bandsEnergy()-41,48"        
## [323] "fBodyAcc-bandsEnergy()-49,56"        
## [324] "fBodyAcc-bandsEnergy()-57,64"        
## [325] "fBodyAcc-bandsEnergy()-1,16"         
## [326] "fBodyAcc-bandsEnergy()-17,32"        
## [327] "fBodyAcc-bandsEnergy()-33,48"        
## [328] "fBodyAcc-bandsEnergy()-49,64"        
## [329] "fBodyAcc-bandsEnergy()-1,24"         
## [330] "fBodyAcc-bandsEnergy()-25,48"        
## [331] "fBodyAcc-bandsEnergy()-1,8"          
## [332] "fBodyAcc-bandsEnergy()-9,16"         
## [333] "fBodyAcc-bandsEnergy()-17,24"        
## [334] "fBodyAcc-bandsEnergy()-25,32"        
## [335] "fBodyAcc-bandsEnergy()-33,40"        
## [336] "fBodyAcc-bandsEnergy()-41,48"        
## [337] "fBodyAcc-bandsEnergy()-49,56"        
## [338] "fBodyAcc-bandsEnergy()-57,64"        
## [339] "fBodyAcc-bandsEnergy()-1,16"         
## [340] "fBodyAcc-bandsEnergy()-17,32"        
## [341] "fBodyAcc-bandsEnergy()-33,48"        
## [342] "fBodyAcc-bandsEnergy()-49,64"        
## [343] "fBodyAcc-bandsEnergy()-1,24"         
## [344] "fBodyAcc-bandsEnergy()-25,48"        
## [345] "fBodyAccJerk-mean()-X"               
## [346] "fBodyAccJerk-mean()-Y"               
## [347] "fBodyAccJerk-mean()-Z"               
## [348] "fBodyAccJerk-std()-X"                
## [349] "fBodyAccJerk-std()-Y"                
## [350] "fBodyAccJerk-std()-Z"                
## [351] "fBodyAccJerk-mad()-X"                
## [352] "fBodyAccJerk-mad()-Y"                
## [353] "fBodyAccJerk-mad()-Z"                
## [354] "fBodyAccJerk-max()-X"                
## [355] "fBodyAccJerk-max()-Y"                
## [356] "fBodyAccJerk-max()-Z"                
## [357] "fBodyAccJerk-min()-X"                
## [358] "fBodyAccJerk-min()-Y"                
## [359] "fBodyAccJerk-min()-Z"                
## [360] "fBodyAccJerk-sma()"                  
## [361] "fBodyAccJerk-energy()-X"             
## [362] "fBodyAccJerk-energy()-Y"             
## [363] "fBodyAccJerk-energy()-Z"             
## [364] "fBodyAccJerk-iqr()-X"                
## [365] "fBodyAccJerk-iqr()-Y"                
## [366] "fBodyAccJerk-iqr()-Z"                
## [367] "fBodyAccJerk-entropy()-X"            
## [368] "fBodyAccJerk-entropy()-Y"            
## [369] "fBodyAccJerk-entropy()-Z"            
## [370] "fBodyAccJerk-maxInds-X"              
## [371] "fBodyAccJerk-maxInds-Y"              
## [372] "fBodyAccJerk-maxInds-Z"              
## [373] "fBodyAccJerk-meanFreq()-X"           
## [374] "fBodyAccJerk-meanFreq()-Y"           
## [375] "fBodyAccJerk-meanFreq()-Z"           
## [376] "fBodyAccJerk-skewness()-X"           
## [377] "fBodyAccJerk-kurtosis()-X"           
## [378] "fBodyAccJerk-skewness()-Y"           
## [379] "fBodyAccJerk-kurtosis()-Y"           
## [380] "fBodyAccJerk-skewness()-Z"           
## [381] "fBodyAccJerk-kurtosis()-Z"           
## [382] "fBodyAccJerk-bandsEnergy()-1,8"      
## [383] "fBodyAccJerk-bandsEnergy()-9,16"     
## [384] "fBodyAccJerk-bandsEnergy()-17,24"    
## [385] "fBodyAccJerk-bandsEnergy()-25,32"    
## [386] "fBodyAccJerk-bandsEnergy()-33,40"    
## [387] "fBodyAccJerk-bandsEnergy()-41,48"    
## [388] "fBodyAccJerk-bandsEnergy()-49,56"    
## [389] "fBodyAccJerk-bandsEnergy()-57,64"    
## [390] "fBodyAccJerk-bandsEnergy()-1,16"     
## [391] "fBodyAccJerk-bandsEnergy()-17,32"    
## [392] "fBodyAccJerk-bandsEnergy()-33,48"    
## [393] "fBodyAccJerk-bandsEnergy()-49,64"    
## [394] "fBodyAccJerk-bandsEnergy()-1,24"     
## [395] "fBodyAccJerk-bandsEnergy()-25,48"    
## [396] "fBodyAccJerk-bandsEnergy()-1,8"      
## [397] "fBodyAccJerk-bandsEnergy()-9,16"     
## [398] "fBodyAccJerk-bandsEnergy()-17,24"    
## [399] "fBodyAccJerk-bandsEnergy()-25,32"    
## [400] "fBodyAccJerk-bandsEnergy()-33,40"    
## [401] "fBodyAccJerk-bandsEnergy()-41,48"    
## [402] "fBodyAccJerk-bandsEnergy()-49,56"    
## [403] "fBodyAccJerk-bandsEnergy()-57,64"    
## [404] "fBodyAccJerk-bandsEnergy()-1,16"     
## [405] "fBodyAccJerk-bandsEnergy()-17,32"    
## [406] "fBodyAccJerk-bandsEnergy()-33,48"    
## [407] "fBodyAccJerk-bandsEnergy()-49,64"    
## [408] "fBodyAccJerk-bandsEnergy()-1,24"     
## [409] "fBodyAccJerk-bandsEnergy()-25,48"    
## [410] "fBodyAccJerk-bandsEnergy()-1,8"      
## [411] "fBodyAccJerk-bandsEnergy()-9,16"     
## [412] "fBodyAccJerk-bandsEnergy()-17,24"    
## [413] "fBodyAccJerk-bandsEnergy()-25,32"    
## [414] "fBodyAccJerk-bandsEnergy()-33,40"    
## [415] "fBodyAccJerk-bandsEnergy()-41,48"    
## [416] "fBodyAccJerk-bandsEnergy()-49,56"    
## [417] "fBodyAccJerk-bandsEnergy()-57,64"    
## [418] "fBodyAccJerk-bandsEnergy()-1,16"     
## [419] "fBodyAccJerk-bandsEnergy()-17,32"    
## [420] "fBodyAccJerk-bandsEnergy()-33,48"    
## [421] "fBodyAccJerk-bandsEnergy()-49,64"    
## [422] "fBodyAccJerk-bandsEnergy()-1,24"     
## [423] "fBodyAccJerk-bandsEnergy()-25,48"    
## [424] "fBodyGyro-mean()-X"                  
## [425] "fBodyGyro-mean()-Y"                  
## [426] "fBodyGyro-mean()-Z"                  
## [427] "fBodyGyro-std()-X"                   
## [428] "fBodyGyro-std()-Y"                   
## [429] "fBodyGyro-std()-Z"                   
## [430] "fBodyGyro-mad()-X"                   
## [431] "fBodyGyro-mad()-Y"                   
## [432] "fBodyGyro-mad()-Z"                   
## [433] "fBodyGyro-max()-X"                   
## [434] "fBodyGyro-max()-Y"                   
## [435] "fBodyGyro-max()-Z"                   
## [436] "fBodyGyro-min()-X"                   
## [437] "fBodyGyro-min()-Y"                   
## [438] "fBodyGyro-min()-Z"                   
## [439] "fBodyGyro-sma()"                     
## [440] "fBodyGyro-energy()-X"                
## [441] "fBodyGyro-energy()-Y"                
## [442] "fBodyGyro-energy()-Z"                
## [443] "fBodyGyro-iqr()-X"                   
## [444] "fBodyGyro-iqr()-Y"                   
## [445] "fBodyGyro-iqr()-Z"                   
## [446] "fBodyGyro-entropy()-X"               
## [447] "fBodyGyro-entropy()-Y"               
## [448] "fBodyGyro-entropy()-Z"               
## [449] "fBodyGyro-maxInds-X"                 
## [450] "fBodyGyro-maxInds-Y"                 
## [451] "fBodyGyro-maxInds-Z"                 
## [452] "fBodyGyro-meanFreq()-X"              
## [453] "fBodyGyro-meanFreq()-Y"              
## [454] "fBodyGyro-meanFreq()-Z"              
## [455] "fBodyGyro-skewness()-X"              
## [456] "fBodyGyro-kurtosis()-X"              
## [457] "fBodyGyro-skewness()-Y"              
## [458] "fBodyGyro-kurtosis()-Y"              
## [459] "fBodyGyro-skewness()-Z"              
## [460] "fBodyGyro-kurtosis()-Z"              
## [461] "fBodyGyro-bandsEnergy()-1,8"         
## [462] "fBodyGyro-bandsEnergy()-9,16"        
## [463] "fBodyGyro-bandsEnergy()-17,24"       
## [464] "fBodyGyro-bandsEnergy()-25,32"       
## [465] "fBodyGyro-bandsEnergy()-33,40"       
## [466] "fBodyGyro-bandsEnergy()-41,48"       
## [467] "fBodyGyro-bandsEnergy()-49,56"       
## [468] "fBodyGyro-bandsEnergy()-57,64"       
## [469] "fBodyGyro-bandsEnergy()-1,16"        
## [470] "fBodyGyro-bandsEnergy()-17,32"       
## [471] "fBodyGyro-bandsEnergy()-33,48"       
## [472] "fBodyGyro-bandsEnergy()-49,64"       
## [473] "fBodyGyro-bandsEnergy()-1,24"        
## [474] "fBodyGyro-bandsEnergy()-25,48"       
## [475] "fBodyGyro-bandsEnergy()-1,8"         
## [476] "fBodyGyro-bandsEnergy()-9,16"        
## [477] "fBodyGyro-bandsEnergy()-17,24"       
## [478] "fBodyGyro-bandsEnergy()-25,32"       
## [479] "fBodyGyro-bandsEnergy()-33,40"       
## [480] "fBodyGyro-bandsEnergy()-41,48"       
## [481] "fBodyGyro-bandsEnergy()-49,56"       
## [482] "fBodyGyro-bandsEnergy()-57,64"       
## [483] "fBodyGyro-bandsEnergy()-1,16"        
## [484] "fBodyGyro-bandsEnergy()-17,32"       
## [485] "fBodyGyro-bandsEnergy()-33,48"       
## [486] "fBodyGyro-bandsEnergy()-49,64"       
## [487] "fBodyGyro-bandsEnergy()-1,24"        
## [488] "fBodyGyro-bandsEnergy()-25,48"       
## [489] "fBodyGyro-bandsEnergy()-1,8"         
## [490] "fBodyGyro-bandsEnergy()-9,16"        
## [491] "fBodyGyro-bandsEnergy()-17,24"       
## [492] "fBodyGyro-bandsEnergy()-25,32"       
## [493] "fBodyGyro-bandsEnergy()-33,40"       
## [494] "fBodyGyro-bandsEnergy()-41,48"       
## [495] "fBodyGyro-bandsEnergy()-49,56"       
## [496] "fBodyGyro-bandsEnergy()-57,64"       
## [497] "fBodyGyro-bandsEnergy()-1,16"        
## [498] "fBodyGyro-bandsEnergy()-17,32"       
## [499] "fBodyGyro-bandsEnergy()-33,48"       
## [500] "fBodyGyro-bandsEnergy()-49,64"       
## [501] "fBodyGyro-bandsEnergy()-1,24"        
## [502] "fBodyGyro-bandsEnergy()-25,48"       
## [503] "fBodyAccMag-mean()"                  
## [504] "fBodyAccMag-std()"                   
## [505] "fBodyAccMag-mad()"                   
## [506] "fBodyAccMag-max()"                   
## [507] "fBodyAccMag-min()"                   
## [508] "fBodyAccMag-sma()"                   
## [509] "fBodyAccMag-energy()"                
## [510] "fBodyAccMag-iqr()"                   
## [511] "fBodyAccMag-entropy()"               
## [512] "fBodyAccMag-maxInds"                 
## [513] "fBodyAccMag-meanFreq()"              
## [514] "fBodyAccMag-skewness()"              
## [515] "fBodyAccMag-kurtosis()"              
## [516] "fBodyBodyAccJerkMag-mean()"          
## [517] "fBodyBodyAccJerkMag-std()"           
## [518] "fBodyBodyAccJerkMag-mad()"           
## [519] "fBodyBodyAccJerkMag-max()"           
## [520] "fBodyBodyAccJerkMag-min()"           
## [521] "fBodyBodyAccJerkMag-sma()"           
## [522] "fBodyBodyAccJerkMag-energy()"        
## [523] "fBodyBodyAccJerkMag-iqr()"           
## [524] "fBodyBodyAccJerkMag-entropy()"       
## [525] "fBodyBodyAccJerkMag-maxInds"         
## [526] "fBodyBodyAccJerkMag-meanFreq()"      
## [527] "fBodyBodyAccJerkMag-skewness()"      
## [528] "fBodyBodyAccJerkMag-kurtosis()"      
## [529] "fBodyBodyGyroMag-mean()"             
## [530] "fBodyBodyGyroMag-std()"              
## [531] "fBodyBodyGyroMag-mad()"              
## [532] "fBodyBodyGyroMag-max()"              
## [533] "fBodyBodyGyroMag-min()"              
## [534] "fBodyBodyGyroMag-sma()"              
## [535] "fBodyBodyGyroMag-energy()"           
## [536] "fBodyBodyGyroMag-iqr()"              
## [537] "fBodyBodyGyroMag-entropy()"          
## [538] "fBodyBodyGyroMag-maxInds"            
## [539] "fBodyBodyGyroMag-meanFreq()"         
## [540] "fBodyBodyGyroMag-skewness()"         
## [541] "fBodyBodyGyroMag-kurtosis()"         
## [542] "fBodyBodyGyroJerkMag-mean()"         
## [543] "fBodyBodyGyroJerkMag-std()"          
## [544] "fBodyBodyGyroJerkMag-mad()"          
## [545] "fBodyBodyGyroJerkMag-max()"          
## [546] "fBodyBodyGyroJerkMag-min()"          
## [547] "fBodyBodyGyroJerkMag-sma()"          
## [548] "fBodyBodyGyroJerkMag-energy()"       
## [549] "fBodyBodyGyroJerkMag-iqr()"          
## [550] "fBodyBodyGyroJerkMag-entropy()"      
## [551] "fBodyBodyGyroJerkMag-maxInds"        
## [552] "fBodyBodyGyroJerkMag-meanFreq()"     
## [553] "fBodyBodyGyroJerkMag-skewness()"     
## [554] "fBodyBodyGyroJerkMag-kurtosis()"     
## [555] "angle(tBodyAccMean,gravity)"         
## [556] "angle(tBodyAccJerkMean),gravityMean)"
## [557] "angle(tBodyGyroMean,gravityMean)"    
## [558] "angle(tBodyGyroJerkMean,gravityMean)"
## [559] "angle(X,gravityMean)"                
## [560] "angle(Y,gravityMean)"                
## [561] "angle(Z,gravityMean)"                
## [562] "subject"                             
## [563] "activity"
```

```r
table(is.na(samsungData))  ## no NAs
```

```
## 
##   FALSE 
## 4139176
```

```r
table(samsungData$subject)
```

```
## 
##   1   3   5   6   7   8  11  14  15  16  17  19  21  22  23  25  26  27 
## 347 341 302 325 308 281 316 323 328 366 368 360 408 321 372 409 392 376 
##  28  29  30 
## 382 344 383
```

There are no NAs found.
21 subjects total, with numeric identifiers.

### Data Munging
Make variable names syntactically correct by removing parentheses, commas, etc.

```r
nameVec <- make.names(names(samsungData), unique = TRUE)
names(samsungData) <- nameVec
names(samsungData)
```

```
##   [1] "tBodyAcc.mean...X"                   
##   [2] "tBodyAcc.mean...Y"                   
##   [3] "tBodyAcc.mean...Z"                   
##   [4] "tBodyAcc.std...X"                    
##   [5] "tBodyAcc.std...Y"                    
##   [6] "tBodyAcc.std...Z"                    
##   [7] "tBodyAcc.mad...X"                    
##   [8] "tBodyAcc.mad...Y"                    
##   [9] "tBodyAcc.mad...Z"                    
##  [10] "tBodyAcc.max...X"                    
##  [11] "tBodyAcc.max...Y"                    
##  [12] "tBodyAcc.max...Z"                    
##  [13] "tBodyAcc.min...X"                    
##  [14] "tBodyAcc.min...Y"                    
##  [15] "tBodyAcc.min...Z"                    
##  [16] "tBodyAcc.sma.."                      
##  [17] "tBodyAcc.energy...X"                 
##  [18] "tBodyAcc.energy...Y"                 
##  [19] "tBodyAcc.energy...Z"                 
##  [20] "tBodyAcc.iqr...X"                    
##  [21] "tBodyAcc.iqr...Y"                    
##  [22] "tBodyAcc.iqr...Z"                    
##  [23] "tBodyAcc.entropy...X"                
##  [24] "tBodyAcc.entropy...Y"                
##  [25] "tBodyAcc.entropy...Z"                
##  [26] "tBodyAcc.arCoeff...X.1"              
##  [27] "tBodyAcc.arCoeff...X.2"              
##  [28] "tBodyAcc.arCoeff...X.3"              
##  [29] "tBodyAcc.arCoeff...X.4"              
##  [30] "tBodyAcc.arCoeff...Y.1"              
##  [31] "tBodyAcc.arCoeff...Y.2"              
##  [32] "tBodyAcc.arCoeff...Y.3"              
##  [33] "tBodyAcc.arCoeff...Y.4"              
##  [34] "tBodyAcc.arCoeff...Z.1"              
##  [35] "tBodyAcc.arCoeff...Z.2"              
##  [36] "tBodyAcc.arCoeff...Z.3"              
##  [37] "tBodyAcc.arCoeff...Z.4"              
##  [38] "tBodyAcc.correlation...X.Y"          
##  [39] "tBodyAcc.correlation...X.Z"          
##  [40] "tBodyAcc.correlation...Y.Z"          
##  [41] "tGravityAcc.mean...X"                
##  [42] "tGravityAcc.mean...Y"                
##  [43] "tGravityAcc.mean...Z"                
##  [44] "tGravityAcc.std...X"                 
##  [45] "tGravityAcc.std...Y"                 
##  [46] "tGravityAcc.std...Z"                 
##  [47] "tGravityAcc.mad...X"                 
##  [48] "tGravityAcc.mad...Y"                 
##  [49] "tGravityAcc.mad...Z"                 
##  [50] "tGravityAcc.max...X"                 
##  [51] "tGravityAcc.max...Y"                 
##  [52] "tGravityAcc.max...Z"                 
##  [53] "tGravityAcc.min...X"                 
##  [54] "tGravityAcc.min...Y"                 
##  [55] "tGravityAcc.min...Z"                 
##  [56] "tGravityAcc.sma.."                   
##  [57] "tGravityAcc.energy...X"              
##  [58] "tGravityAcc.energy...Y"              
##  [59] "tGravityAcc.energy...Z"              
##  [60] "tGravityAcc.iqr...X"                 
##  [61] "tGravityAcc.iqr...Y"                 
##  [62] "tGravityAcc.iqr...Z"                 
##  [63] "tGravityAcc.entropy...X"             
##  [64] "tGravityAcc.entropy...Y"             
##  [65] "tGravityAcc.entropy...Z"             
##  [66] "tGravityAcc.arCoeff...X.1"           
##  [67] "tGravityAcc.arCoeff...X.2"           
##  [68] "tGravityAcc.arCoeff...X.3"           
##  [69] "tGravityAcc.arCoeff...X.4"           
##  [70] "tGravityAcc.arCoeff...Y.1"           
##  [71] "tGravityAcc.arCoeff...Y.2"           
##  [72] "tGravityAcc.arCoeff...Y.3"           
##  [73] "tGravityAcc.arCoeff...Y.4"           
##  [74] "tGravityAcc.arCoeff...Z.1"           
##  [75] "tGravityAcc.arCoeff...Z.2"           
##  [76] "tGravityAcc.arCoeff...Z.3"           
##  [77] "tGravityAcc.arCoeff...Z.4"           
##  [78] "tGravityAcc.correlation...X.Y"       
##  [79] "tGravityAcc.correlation...X.Z"       
##  [80] "tGravityAcc.correlation...Y.Z"       
##  [81] "tBodyAccJerk.mean...X"               
##  [82] "tBodyAccJerk.mean...Y"               
##  [83] "tBodyAccJerk.mean...Z"               
##  [84] "tBodyAccJerk.std...X"                
##  [85] "tBodyAccJerk.std...Y"                
##  [86] "tBodyAccJerk.std...Z"                
##  [87] "tBodyAccJerk.mad...X"                
##  [88] "tBodyAccJerk.mad...Y"                
##  [89] "tBodyAccJerk.mad...Z"                
##  [90] "tBodyAccJerk.max...X"                
##  [91] "tBodyAccJerk.max...Y"                
##  [92] "tBodyAccJerk.max...Z"                
##  [93] "tBodyAccJerk.min...X"                
##  [94] "tBodyAccJerk.min...Y"                
##  [95] "tBodyAccJerk.min...Z"                
##  [96] "tBodyAccJerk.sma.."                  
##  [97] "tBodyAccJerk.energy...X"             
##  [98] "tBodyAccJerk.energy...Y"             
##  [99] "tBodyAccJerk.energy...Z"             
## [100] "tBodyAccJerk.iqr...X"                
## [101] "tBodyAccJerk.iqr...Y"                
## [102] "tBodyAccJerk.iqr...Z"                
## [103] "tBodyAccJerk.entropy...X"            
## [104] "tBodyAccJerk.entropy...Y"            
## [105] "tBodyAccJerk.entropy...Z"            
## [106] "tBodyAccJerk.arCoeff...X.1"          
## [107] "tBodyAccJerk.arCoeff...X.2"          
## [108] "tBodyAccJerk.arCoeff...X.3"          
## [109] "tBodyAccJerk.arCoeff...X.4"          
## [110] "tBodyAccJerk.arCoeff...Y.1"          
## [111] "tBodyAccJerk.arCoeff...Y.2"          
## [112] "tBodyAccJerk.arCoeff...Y.3"          
## [113] "tBodyAccJerk.arCoeff...Y.4"          
## [114] "tBodyAccJerk.arCoeff...Z.1"          
## [115] "tBodyAccJerk.arCoeff...Z.2"          
## [116] "tBodyAccJerk.arCoeff...Z.3"          
## [117] "tBodyAccJerk.arCoeff...Z.4"          
## [118] "tBodyAccJerk.correlation...X.Y"      
## [119] "tBodyAccJerk.correlation...X.Z"      
## [120] "tBodyAccJerk.correlation...Y.Z"      
## [121] "tBodyGyro.mean...X"                  
## [122] "tBodyGyro.mean...Y"                  
## [123] "tBodyGyro.mean...Z"                  
## [124] "tBodyGyro.std...X"                   
## [125] "tBodyGyro.std...Y"                   
## [126] "tBodyGyro.std...Z"                   
## [127] "tBodyGyro.mad...X"                   
## [128] "tBodyGyro.mad...Y"                   
## [129] "tBodyGyro.mad...Z"                   
## [130] "tBodyGyro.max...X"                   
## [131] "tBodyGyro.max...Y"                   
## [132] "tBodyGyro.max...Z"                   
## [133] "tBodyGyro.min...X"                   
## [134] "tBodyGyro.min...Y"                   
## [135] "tBodyGyro.min...Z"                   
## [136] "tBodyGyro.sma.."                     
## [137] "tBodyGyro.energy...X"                
## [138] "tBodyGyro.energy...Y"                
## [139] "tBodyGyro.energy...Z"                
## [140] "tBodyGyro.iqr...X"                   
## [141] "tBodyGyro.iqr...Y"                   
## [142] "tBodyGyro.iqr...Z"                   
## [143] "tBodyGyro.entropy...X"               
## [144] "tBodyGyro.entropy...Y"               
## [145] "tBodyGyro.entropy...Z"               
## [146] "tBodyGyro.arCoeff...X.1"             
## [147] "tBodyGyro.arCoeff...X.2"             
## [148] "tBodyGyro.arCoeff...X.3"             
## [149] "tBodyGyro.arCoeff...X.4"             
## [150] "tBodyGyro.arCoeff...Y.1"             
## [151] "tBodyGyro.arCoeff...Y.2"             
## [152] "tBodyGyro.arCoeff...Y.3"             
## [153] "tBodyGyro.arCoeff...Y.4"             
## [154] "tBodyGyro.arCoeff...Z.1"             
## [155] "tBodyGyro.arCoeff...Z.2"             
## [156] "tBodyGyro.arCoeff...Z.3"             
## [157] "tBodyGyro.arCoeff...Z.4"             
## [158] "tBodyGyro.correlation...X.Y"         
## [159] "tBodyGyro.correlation...X.Z"         
## [160] "tBodyGyro.correlation...Y.Z"         
## [161] "tBodyGyroJerk.mean...X"              
## [162] "tBodyGyroJerk.mean...Y"              
## [163] "tBodyGyroJerk.mean...Z"              
## [164] "tBodyGyroJerk.std...X"               
## [165] "tBodyGyroJerk.std...Y"               
## [166] "tBodyGyroJerk.std...Z"               
## [167] "tBodyGyroJerk.mad...X"               
## [168] "tBodyGyroJerk.mad...Y"               
## [169] "tBodyGyroJerk.mad...Z"               
## [170] "tBodyGyroJerk.max...X"               
## [171] "tBodyGyroJerk.max...Y"               
## [172] "tBodyGyroJerk.max...Z"               
## [173] "tBodyGyroJerk.min...X"               
## [174] "tBodyGyroJerk.min...Y"               
## [175] "tBodyGyroJerk.min...Z"               
## [176] "tBodyGyroJerk.sma.."                 
## [177] "tBodyGyroJerk.energy...X"            
## [178] "tBodyGyroJerk.energy...Y"            
## [179] "tBodyGyroJerk.energy...Z"            
## [180] "tBodyGyroJerk.iqr...X"               
## [181] "tBodyGyroJerk.iqr...Y"               
## [182] "tBodyGyroJerk.iqr...Z"               
## [183] "tBodyGyroJerk.entropy...X"           
## [184] "tBodyGyroJerk.entropy...Y"           
## [185] "tBodyGyroJerk.entropy...Z"           
## [186] "tBodyGyroJerk.arCoeff...X.1"         
## [187] "tBodyGyroJerk.arCoeff...X.2"         
## [188] "tBodyGyroJerk.arCoeff...X.3"         
## [189] "tBodyGyroJerk.arCoeff...X.4"         
## [190] "tBodyGyroJerk.arCoeff...Y.1"         
## [191] "tBodyGyroJerk.arCoeff...Y.2"         
## [192] "tBodyGyroJerk.arCoeff...Y.3"         
## [193] "tBodyGyroJerk.arCoeff...Y.4"         
## [194] "tBodyGyroJerk.arCoeff...Z.1"         
## [195] "tBodyGyroJerk.arCoeff...Z.2"         
## [196] "tBodyGyroJerk.arCoeff...Z.3"         
## [197] "tBodyGyroJerk.arCoeff...Z.4"         
## [198] "tBodyGyroJerk.correlation...X.Y"     
## [199] "tBodyGyroJerk.correlation...X.Z"     
## [200] "tBodyGyroJerk.correlation...Y.Z"     
## [201] "tBodyAccMag.mean.."                  
## [202] "tBodyAccMag.std.."                   
## [203] "tBodyAccMag.mad.."                   
## [204] "tBodyAccMag.max.."                   
## [205] "tBodyAccMag.min.."                   
## [206] "tBodyAccMag.sma.."                   
## [207] "tBodyAccMag.energy.."                
## [208] "tBodyAccMag.iqr.."                   
## [209] "tBodyAccMag.entropy.."               
## [210] "tBodyAccMag.arCoeff..1"              
## [211] "tBodyAccMag.arCoeff..2"              
## [212] "tBodyAccMag.arCoeff..3"              
## [213] "tBodyAccMag.arCoeff..4"              
## [214] "tGravityAccMag.mean.."               
## [215] "tGravityAccMag.std.."                
## [216] "tGravityAccMag.mad.."                
## [217] "tGravityAccMag.max.."                
## [218] "tGravityAccMag.min.."                
## [219] "tGravityAccMag.sma.."                
## [220] "tGravityAccMag.energy.."             
## [221] "tGravityAccMag.iqr.."                
## [222] "tGravityAccMag.entropy.."            
## [223] "tGravityAccMag.arCoeff..1"           
## [224] "tGravityAccMag.arCoeff..2"           
## [225] "tGravityAccMag.arCoeff..3"           
## [226] "tGravityAccMag.arCoeff..4"           
## [227] "tBodyAccJerkMag.mean.."              
## [228] "tBodyAccJerkMag.std.."               
## [229] "tBodyAccJerkMag.mad.."               
## [230] "tBodyAccJerkMag.max.."               
## [231] "tBodyAccJerkMag.min.."               
## [232] "tBodyAccJerkMag.sma.."               
## [233] "tBodyAccJerkMag.energy.."            
## [234] "tBodyAccJerkMag.iqr.."               
## [235] "tBodyAccJerkMag.entropy.."           
## [236] "tBodyAccJerkMag.arCoeff..1"          
## [237] "tBodyAccJerkMag.arCoeff..2"          
## [238] "tBodyAccJerkMag.arCoeff..3"          
## [239] "tBodyAccJerkMag.arCoeff..4"          
## [240] "tBodyGyroMag.mean.."                 
## [241] "tBodyGyroMag.std.."                  
## [242] "tBodyGyroMag.mad.."                  
## [243] "tBodyGyroMag.max.."                  
## [244] "tBodyGyroMag.min.."                  
## [245] "tBodyGyroMag.sma.."                  
## [246] "tBodyGyroMag.energy.."               
## [247] "tBodyGyroMag.iqr.."                  
## [248] "tBodyGyroMag.entropy.."              
## [249] "tBodyGyroMag.arCoeff..1"             
## [250] "tBodyGyroMag.arCoeff..2"             
## [251] "tBodyGyroMag.arCoeff..3"             
## [252] "tBodyGyroMag.arCoeff..4"             
## [253] "tBodyGyroJerkMag.mean.."             
## [254] "tBodyGyroJerkMag.std.."              
## [255] "tBodyGyroJerkMag.mad.."              
## [256] "tBodyGyroJerkMag.max.."              
## [257] "tBodyGyroJerkMag.min.."              
## [258] "tBodyGyroJerkMag.sma.."              
## [259] "tBodyGyroJerkMag.energy.."           
## [260] "tBodyGyroJerkMag.iqr.."              
## [261] "tBodyGyroJerkMag.entropy.."          
## [262] "tBodyGyroJerkMag.arCoeff..1"         
## [263] "tBodyGyroJerkMag.arCoeff..2"         
## [264] "tBodyGyroJerkMag.arCoeff..3"         
## [265] "tBodyGyroJerkMag.arCoeff..4"         
## [266] "fBodyAcc.mean...X"                   
## [267] "fBodyAcc.mean...Y"                   
## [268] "fBodyAcc.mean...Z"                   
## [269] "fBodyAcc.std...X"                    
## [270] "fBodyAcc.std...Y"                    
## [271] "fBodyAcc.std...Z"                    
## [272] "fBodyAcc.mad...X"                    
## [273] "fBodyAcc.mad...Y"                    
## [274] "fBodyAcc.mad...Z"                    
## [275] "fBodyAcc.max...X"                    
## [276] "fBodyAcc.max...Y"                    
## [277] "fBodyAcc.max...Z"                    
## [278] "fBodyAcc.min...X"                    
## [279] "fBodyAcc.min...Y"                    
## [280] "fBodyAcc.min...Z"                    
## [281] "fBodyAcc.sma.."                      
## [282] "fBodyAcc.energy...X"                 
## [283] "fBodyAcc.energy...Y"                 
## [284] "fBodyAcc.energy...Z"                 
## [285] "fBodyAcc.iqr...X"                    
## [286] "fBodyAcc.iqr...Y"                    
## [287] "fBodyAcc.iqr...Z"                    
## [288] "fBodyAcc.entropy...X"                
## [289] "fBodyAcc.entropy...Y"                
## [290] "fBodyAcc.entropy...Z"                
## [291] "fBodyAcc.maxInds.X"                  
## [292] "fBodyAcc.maxInds.Y"                  
## [293] "fBodyAcc.maxInds.Z"                  
## [294] "fBodyAcc.meanFreq...X"               
## [295] "fBodyAcc.meanFreq...Y"               
## [296] "fBodyAcc.meanFreq...Z"               
## [297] "fBodyAcc.skewness...X"               
## [298] "fBodyAcc.kurtosis...X"               
## [299] "fBodyAcc.skewness...Y"               
## [300] "fBodyAcc.kurtosis...Y"               
## [301] "fBodyAcc.skewness...Z"               
## [302] "fBodyAcc.kurtosis...Z"               
## [303] "fBodyAcc.bandsEnergy...1.8"          
## [304] "fBodyAcc.bandsEnergy...9.16"         
## [305] "fBodyAcc.bandsEnergy...17.24"        
## [306] "fBodyAcc.bandsEnergy...25.32"        
## [307] "fBodyAcc.bandsEnergy...33.40"        
## [308] "fBodyAcc.bandsEnergy...41.48"        
## [309] "fBodyAcc.bandsEnergy...49.56"        
## [310] "fBodyAcc.bandsEnergy...57.64"        
## [311] "fBodyAcc.bandsEnergy...1.16"         
## [312] "fBodyAcc.bandsEnergy...17.32"        
## [313] "fBodyAcc.bandsEnergy...33.48"        
## [314] "fBodyAcc.bandsEnergy...49.64"        
## [315] "fBodyAcc.bandsEnergy...1.24"         
## [316] "fBodyAcc.bandsEnergy...25.48"        
## [317] "fBodyAcc.bandsEnergy...1.8.1"        
## [318] "fBodyAcc.bandsEnergy...9.16.1"       
## [319] "fBodyAcc.bandsEnergy...17.24.1"      
## [320] "fBodyAcc.bandsEnergy...25.32.1"      
## [321] "fBodyAcc.bandsEnergy...33.40.1"      
## [322] "fBodyAcc.bandsEnergy...41.48.1"      
## [323] "fBodyAcc.bandsEnergy...49.56.1"      
## [324] "fBodyAcc.bandsEnergy...57.64.1"      
## [325] "fBodyAcc.bandsEnergy...1.16.1"       
## [326] "fBodyAcc.bandsEnergy...17.32.1"      
## [327] "fBodyAcc.bandsEnergy...33.48.1"      
## [328] "fBodyAcc.bandsEnergy...49.64.1"      
## [329] "fBodyAcc.bandsEnergy...1.24.1"       
## [330] "fBodyAcc.bandsEnergy...25.48.1"      
## [331] "fBodyAcc.bandsEnergy...1.8.2"        
## [332] "fBodyAcc.bandsEnergy...9.16.2"       
## [333] "fBodyAcc.bandsEnergy...17.24.2"      
## [334] "fBodyAcc.bandsEnergy...25.32.2"      
## [335] "fBodyAcc.bandsEnergy...33.40.2"      
## [336] "fBodyAcc.bandsEnergy...41.48.2"      
## [337] "fBodyAcc.bandsEnergy...49.56.2"      
## [338] "fBodyAcc.bandsEnergy...57.64.2"      
## [339] "fBodyAcc.bandsEnergy...1.16.2"       
## [340] "fBodyAcc.bandsEnergy...17.32.2"      
## [341] "fBodyAcc.bandsEnergy...33.48.2"      
## [342] "fBodyAcc.bandsEnergy...49.64.2"      
## [343] "fBodyAcc.bandsEnergy...1.24.2"       
## [344] "fBodyAcc.bandsEnergy...25.48.2"      
## [345] "fBodyAccJerk.mean...X"               
## [346] "fBodyAccJerk.mean...Y"               
## [347] "fBodyAccJerk.mean...Z"               
## [348] "fBodyAccJerk.std...X"                
## [349] "fBodyAccJerk.std...Y"                
## [350] "fBodyAccJerk.std...Z"                
## [351] "fBodyAccJerk.mad...X"                
## [352] "fBodyAccJerk.mad...Y"                
## [353] "fBodyAccJerk.mad...Z"                
## [354] "fBodyAccJerk.max...X"                
## [355] "fBodyAccJerk.max...Y"                
## [356] "fBodyAccJerk.max...Z"                
## [357] "fBodyAccJerk.min...X"                
## [358] "fBodyAccJerk.min...Y"                
## [359] "fBodyAccJerk.min...Z"                
## [360] "fBodyAccJerk.sma.."                  
## [361] "fBodyAccJerk.energy...X"             
## [362] "fBodyAccJerk.energy...Y"             
## [363] "fBodyAccJerk.energy...Z"             
## [364] "fBodyAccJerk.iqr...X"                
## [365] "fBodyAccJerk.iqr...Y"                
## [366] "fBodyAccJerk.iqr...Z"                
## [367] "fBodyAccJerk.entropy...X"            
## [368] "fBodyAccJerk.entropy...Y"            
## [369] "fBodyAccJerk.entropy...Z"            
## [370] "fBodyAccJerk.maxInds.X"              
## [371] "fBodyAccJerk.maxInds.Y"              
## [372] "fBodyAccJerk.maxInds.Z"              
## [373] "fBodyAccJerk.meanFreq...X"           
## [374] "fBodyAccJerk.meanFreq...Y"           
## [375] "fBodyAccJerk.meanFreq...Z"           
## [376] "fBodyAccJerk.skewness...X"           
## [377] "fBodyAccJerk.kurtosis...X"           
## [378] "fBodyAccJerk.skewness...Y"           
## [379] "fBodyAccJerk.kurtosis...Y"           
## [380] "fBodyAccJerk.skewness...Z"           
## [381] "fBodyAccJerk.kurtosis...Z"           
## [382] "fBodyAccJerk.bandsEnergy...1.8"      
## [383] "fBodyAccJerk.bandsEnergy...9.16"     
## [384] "fBodyAccJerk.bandsEnergy...17.24"    
## [385] "fBodyAccJerk.bandsEnergy...25.32"    
## [386] "fBodyAccJerk.bandsEnergy...33.40"    
## [387] "fBodyAccJerk.bandsEnergy...41.48"    
## [388] "fBodyAccJerk.bandsEnergy...49.56"    
## [389] "fBodyAccJerk.bandsEnergy...57.64"    
## [390] "fBodyAccJerk.bandsEnergy...1.16"     
## [391] "fBodyAccJerk.bandsEnergy...17.32"    
## [392] "fBodyAccJerk.bandsEnergy...33.48"    
## [393] "fBodyAccJerk.bandsEnergy...49.64"    
## [394] "fBodyAccJerk.bandsEnergy...1.24"     
## [395] "fBodyAccJerk.bandsEnergy...25.48"    
## [396] "fBodyAccJerk.bandsEnergy...1.8.1"    
## [397] "fBodyAccJerk.bandsEnergy...9.16.1"   
## [398] "fBodyAccJerk.bandsEnergy...17.24.1"  
## [399] "fBodyAccJerk.bandsEnergy...25.32.1"  
## [400] "fBodyAccJerk.bandsEnergy...33.40.1"  
## [401] "fBodyAccJerk.bandsEnergy...41.48.1"  
## [402] "fBodyAccJerk.bandsEnergy...49.56.1"  
## [403] "fBodyAccJerk.bandsEnergy...57.64.1"  
## [404] "fBodyAccJerk.bandsEnergy...1.16.1"   
## [405] "fBodyAccJerk.bandsEnergy...17.32.1"  
## [406] "fBodyAccJerk.bandsEnergy...33.48.1"  
## [407] "fBodyAccJerk.bandsEnergy...49.64.1"  
## [408] "fBodyAccJerk.bandsEnergy...1.24.1"   
## [409] "fBodyAccJerk.bandsEnergy...25.48.1"  
## [410] "fBodyAccJerk.bandsEnergy...1.8.2"    
## [411] "fBodyAccJerk.bandsEnergy...9.16.2"   
## [412] "fBodyAccJerk.bandsEnergy...17.24.2"  
## [413] "fBodyAccJerk.bandsEnergy...25.32.2"  
## [414] "fBodyAccJerk.bandsEnergy...33.40.2"  
## [415] "fBodyAccJerk.bandsEnergy...41.48.2"  
## [416] "fBodyAccJerk.bandsEnergy...49.56.2"  
## [417] "fBodyAccJerk.bandsEnergy...57.64.2"  
## [418] "fBodyAccJerk.bandsEnergy...1.16.2"   
## [419] "fBodyAccJerk.bandsEnergy...17.32.2"  
## [420] "fBodyAccJerk.bandsEnergy...33.48.2"  
## [421] "fBodyAccJerk.bandsEnergy...49.64.2"  
## [422] "fBodyAccJerk.bandsEnergy...1.24.2"   
## [423] "fBodyAccJerk.bandsEnergy...25.48.2"  
## [424] "fBodyGyro.mean...X"                  
## [425] "fBodyGyro.mean...Y"                  
## [426] "fBodyGyro.mean...Z"                  
## [427] "fBodyGyro.std...X"                   
## [428] "fBodyGyro.std...Y"                   
## [429] "fBodyGyro.std...Z"                   
## [430] "fBodyGyro.mad...X"                   
## [431] "fBodyGyro.mad...Y"                   
## [432] "fBodyGyro.mad...Z"                   
## [433] "fBodyGyro.max...X"                   
## [434] "fBodyGyro.max...Y"                   
## [435] "fBodyGyro.max...Z"                   
## [436] "fBodyGyro.min...X"                   
## [437] "fBodyGyro.min...Y"                   
## [438] "fBodyGyro.min...Z"                   
## [439] "fBodyGyro.sma.."                     
## [440] "fBodyGyro.energy...X"                
## [441] "fBodyGyro.energy...Y"                
## [442] "fBodyGyro.energy...Z"                
## [443] "fBodyGyro.iqr...X"                   
## [444] "fBodyGyro.iqr...Y"                   
## [445] "fBodyGyro.iqr...Z"                   
## [446] "fBodyGyro.entropy...X"               
## [447] "fBodyGyro.entropy...Y"               
## [448] "fBodyGyro.entropy...Z"               
## [449] "fBodyGyro.maxInds.X"                 
## [450] "fBodyGyro.maxInds.Y"                 
## [451] "fBodyGyro.maxInds.Z"                 
## [452] "fBodyGyro.meanFreq...X"              
## [453] "fBodyGyro.meanFreq...Y"              
## [454] "fBodyGyro.meanFreq...Z"              
## [455] "fBodyGyro.skewness...X"              
## [456] "fBodyGyro.kurtosis...X"              
## [457] "fBodyGyro.skewness...Y"              
## [458] "fBodyGyro.kurtosis...Y"              
## [459] "fBodyGyro.skewness...Z"              
## [460] "fBodyGyro.kurtosis...Z"              
## [461] "fBodyGyro.bandsEnergy...1.8"         
## [462] "fBodyGyro.bandsEnergy...9.16"        
## [463] "fBodyGyro.bandsEnergy...17.24"       
## [464] "fBodyGyro.bandsEnergy...25.32"       
## [465] "fBodyGyro.bandsEnergy...33.40"       
## [466] "fBodyGyro.bandsEnergy...41.48"       
## [467] "fBodyGyro.bandsEnergy...49.56"       
## [468] "fBodyGyro.bandsEnergy...57.64"       
## [469] "fBodyGyro.bandsEnergy...1.16"        
## [470] "fBodyGyro.bandsEnergy...17.32"       
## [471] "fBodyGyro.bandsEnergy...33.48"       
## [472] "fBodyGyro.bandsEnergy...49.64"       
## [473] "fBodyGyro.bandsEnergy...1.24"        
## [474] "fBodyGyro.bandsEnergy...25.48"       
## [475] "fBodyGyro.bandsEnergy...1.8.1"       
## [476] "fBodyGyro.bandsEnergy...9.16.1"      
## [477] "fBodyGyro.bandsEnergy...17.24.1"     
## [478] "fBodyGyro.bandsEnergy...25.32.1"     
## [479] "fBodyGyro.bandsEnergy...33.40.1"     
## [480] "fBodyGyro.bandsEnergy...41.48.1"     
## [481] "fBodyGyro.bandsEnergy...49.56.1"     
## [482] "fBodyGyro.bandsEnergy...57.64.1"     
## [483] "fBodyGyro.bandsEnergy...1.16.1"      
## [484] "fBodyGyro.bandsEnergy...17.32.1"     
## [485] "fBodyGyro.bandsEnergy...33.48.1"     
## [486] "fBodyGyro.bandsEnergy...49.64.1"     
## [487] "fBodyGyro.bandsEnergy...1.24.1"      
## [488] "fBodyGyro.bandsEnergy...25.48.1"     
## [489] "fBodyGyro.bandsEnergy...1.8.2"       
## [490] "fBodyGyro.bandsEnergy...9.16.2"      
## [491] "fBodyGyro.bandsEnergy...17.24.2"     
## [492] "fBodyGyro.bandsEnergy...25.32.2"     
## [493] "fBodyGyro.bandsEnergy...33.40.2"     
## [494] "fBodyGyro.bandsEnergy...41.48.2"     
## [495] "fBodyGyro.bandsEnergy...49.56.2"     
## [496] "fBodyGyro.bandsEnergy...57.64.2"     
## [497] "fBodyGyro.bandsEnergy...1.16.2"      
## [498] "fBodyGyro.bandsEnergy...17.32.2"     
## [499] "fBodyGyro.bandsEnergy...33.48.2"     
## [500] "fBodyGyro.bandsEnergy...49.64.2"     
## [501] "fBodyGyro.bandsEnergy...1.24.2"      
## [502] "fBodyGyro.bandsEnergy...25.48.2"     
## [503] "fBodyAccMag.mean.."                  
## [504] "fBodyAccMag.std.."                   
## [505] "fBodyAccMag.mad.."                   
## [506] "fBodyAccMag.max.."                   
## [507] "fBodyAccMag.min.."                   
## [508] "fBodyAccMag.sma.."                   
## [509] "fBodyAccMag.energy.."                
## [510] "fBodyAccMag.iqr.."                   
## [511] "fBodyAccMag.entropy.."               
## [512] "fBodyAccMag.maxInds"                 
## [513] "fBodyAccMag.meanFreq.."              
## [514] "fBodyAccMag.skewness.."              
## [515] "fBodyAccMag.kurtosis.."              
## [516] "fBodyBodyAccJerkMag.mean.."          
## [517] "fBodyBodyAccJerkMag.std.."           
## [518] "fBodyBodyAccJerkMag.mad.."           
## [519] "fBodyBodyAccJerkMag.max.."           
## [520] "fBodyBodyAccJerkMag.min.."           
## [521] "fBodyBodyAccJerkMag.sma.."           
## [522] "fBodyBodyAccJerkMag.energy.."        
## [523] "fBodyBodyAccJerkMag.iqr.."           
## [524] "fBodyBodyAccJerkMag.entropy.."       
## [525] "fBodyBodyAccJerkMag.maxInds"         
## [526] "fBodyBodyAccJerkMag.meanFreq.."      
## [527] "fBodyBodyAccJerkMag.skewness.."      
## [528] "fBodyBodyAccJerkMag.kurtosis.."      
## [529] "fBodyBodyGyroMag.mean.."             
## [530] "fBodyBodyGyroMag.std.."              
## [531] "fBodyBodyGyroMag.mad.."              
## [532] "fBodyBodyGyroMag.max.."              
## [533] "fBodyBodyGyroMag.min.."              
## [534] "fBodyBodyGyroMag.sma.."              
## [535] "fBodyBodyGyroMag.energy.."           
## [536] "fBodyBodyGyroMag.iqr.."              
## [537] "fBodyBodyGyroMag.entropy.."          
## [538] "fBodyBodyGyroMag.maxInds"            
## [539] "fBodyBodyGyroMag.meanFreq.."         
## [540] "fBodyBodyGyroMag.skewness.."         
## [541] "fBodyBodyGyroMag.kurtosis.."         
## [542] "fBodyBodyGyroJerkMag.mean.."         
## [543] "fBodyBodyGyroJerkMag.std.."          
## [544] "fBodyBodyGyroJerkMag.mad.."          
## [545] "fBodyBodyGyroJerkMag.max.."          
## [546] "fBodyBodyGyroJerkMag.min.."          
## [547] "fBodyBodyGyroJerkMag.sma.."          
## [548] "fBodyBodyGyroJerkMag.energy.."       
## [549] "fBodyBodyGyroJerkMag.iqr.."          
## [550] "fBodyBodyGyroJerkMag.entropy.."      
## [551] "fBodyBodyGyroJerkMag.maxInds"        
## [552] "fBodyBodyGyroJerkMag.meanFreq.."     
## [553] "fBodyBodyGyroJerkMag.skewness.."     
## [554] "fBodyBodyGyroJerkMag.kurtosis.."     
## [555] "angle.tBodyAccMean.gravity."         
## [556] "angle.tBodyAccJerkMean..gravityMean."
## [557] "angle.tBodyGyroMean.gravityMean."    
## [558] "angle.tBodyGyroJerkMean.gravityMean."
## [559] "angle.X.gravityMean."                
## [560] "angle.Y.gravityMean."                
## [561] "angle.Z.gravityMean."                
## [562] "subject"                             
## [563] "activity"
```



### make Training, Validation,and Test sets
Training and test sets include the require subjects as noted.
training set size has 13 subjects.
validation set and test set sizes are 4 subjects each.

```r
subjects.rest <- c(7, 8, 11, 14, 15, 16, 17, 19, 21, 22, 23, 25, 26)
set.seed(47033)
train1 <- sample(subjects.rest, 9, replace = FALSE)
train1 <- c(train1, c(1, 3, 5, 6))
test1 <- c(27, 28, 29, 30)
notvalid <- c(train1, test1)
# trainSet <- samsungData[samsungData$subject == c(1,3,5,6),]
trainSet <- samsungData[samsungData$subject %in% train1, ]
validateSet <- samsungData[!(samsungData$subject %in% notvalid), ]
testSet <- samsungData[samsungData$subject %in% test1, ]
table(trainSet$subject)
```

```
## 
##   1   3   5   6   7   8  14  16  17  19  21  23  25 
## 347 341 302 325 308 281 323 366 368 360 408 372 409
```

```r
table(validateSet$subject)
```

```
## 
##  11  15  22  26 
## 316 328 321 392
```

```r
table(testSet$subject)
```

```
## 
##  27  28  29  30 
## 376 382 344 383
```


Pick Function
-------------
### use a tree first

```r
library(tree)
train.tree <- tree(factor(activity) ~ ., data = trainSet)
par(mfrow = c(1, 1))
plot(train.tree)
text(train.tree, cex = 0.5)
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-51.png) 

```r
stree.predict <- predict(train.tree, trainSet[, -563])
head(tree.predict)
```

```
## Error: object 'tree.predict' not found
```

```r
table(trainSet$activity, predict(train.tree, type = "class"))
```

```
##           
##            laying sitting standing walk walkdown walkup
##   laying      836       0        0    0        1      0
##   sitting       0     709       61    0        0      0
##   standing      0     142      712    0        0      0
##   walk          0       0        0  672       72     35
##   walkdown      0       0        0    3      592     17
##   walkup        0       0        1   50       44    563
```

```r
par(mfrow = c(2, 1))
plot(cv.tree(train.tree, FUN = prune.tree, method = "misclass"))
plot(cv.tree(train.tree))
```

![plot of chunk unnamed-chunk-5](figure/unnamed-chunk-52.png) 

```r
table(validateSet$activity, predict(train.tree, validateSet[, -563], type = "class"))
```

```
##           
##            laying sitting standing walk walkdown walkup
##   laying      277       0        0    0        0      0
##   sitting       0     252        0    0        0      0
##   standing      0       6      231    0        0      0
##   walk          0       0        0  194        8     16
##   walkdown      0       0        0    0      172      2
##   walkup        0       0        0   19       25    155
```

Resulting tree is OK but not great. It seems to indicate an interest it gravity!

### random Forest

```r
library(randomForest)
```

```
## randomForest 4.6-7
```

```
## Type rfNews() to see new features/changes/bug fixes.
```

```r
set.seed(37043)
train.rf <- randomForest(factor(activity) ~ ., data = trainSet, prox = TRUE)
print(train.rf)
```

```
## 
## Call:
##  randomForest(formula = factor(activity) ~ ., data = trainSet,      prox = TRUE) 
##                Type of random forest: classification
##                      Number of trees: 500
## No. of variables tried at each split: 23
## 
##         OOB estimate of  error rate: 2.02%
## Confusion matrix:
##          laying sitting standing walk walkdown walkup class.error
## laying      837       0        0    0        0      0    0.000000
## sitting       0     745       24    0        0      1    0.032468
## standing      0      39      815    0        0      0    0.045667
## walk          0       0        0  766        8      5    0.016688
## walkdown      0       0        0    3      606      3    0.009804
## walkup        0       0        0    2        6    650    0.012158
```

```r
importance(train.rf)
```

```
##                                      MeanDecreaseGini
## tBodyAcc.mean...X                              0.9904
## tBodyAcc.mean...Y                              1.1726
## tBodyAcc.mean...Z                              0.6323
## tBodyAcc.std...X                              19.9399
## tBodyAcc.std...Y                               2.0624
## tBodyAcc.std...Z                               1.9510
## tBodyAcc.mad...X                              18.1428
## tBodyAcc.mad...Y                               2.0724
## tBodyAcc.mad...Z                               2.0811
## tBodyAcc.max...X                              36.3353
## tBodyAcc.max...Y                               1.3978
## tBodyAcc.max...Z                               1.3979
## tBodyAcc.min...X                               2.6939
## tBodyAcc.min...Y                               1.2330
## tBodyAcc.min...Z                               1.1353
## tBodyAcc.sma..                                 2.4998
## tBodyAcc.energy...X                           18.4121
## tBodyAcc.energy...Y                            2.5353
## tBodyAcc.energy...Z                            1.8352
## tBodyAcc.iqr...X                               4.6632
## tBodyAcc.iqr...Y                               1.9749
## tBodyAcc.iqr...Z                               1.6689
## tBodyAcc.entropy...X                           2.6334
## tBodyAcc.entropy...Y                           1.1957
## tBodyAcc.entropy...Z                           1.3263
## tBodyAcc.arCoeff...X.1                         1.1679
## tBodyAcc.arCoeff...X.2                         0.7648
## tBodyAcc.arCoeff...X.3                         0.9204
## tBodyAcc.arCoeff...X.4                         1.3996
## tBodyAcc.arCoeff...Y.1                         1.0153
## tBodyAcc.arCoeff...Y.2                         0.7821
## tBodyAcc.arCoeff...Y.3                         0.8236
## tBodyAcc.arCoeff...Y.4                         0.8498
## tBodyAcc.arCoeff...Z.1                         0.8160
## tBodyAcc.arCoeff...Z.2                         0.6603
## tBodyAcc.arCoeff...Z.3                         0.7674
## tBodyAcc.arCoeff...Z.4                         1.2318
## tBodyAcc.correlation...X.Y                    19.5010
## tBodyAcc.correlation...X.Z                     5.9311
## tBodyAcc.correlation...Y.Z                    11.3223
## tGravityAcc.mean...X                          94.9143
## tGravityAcc.mean...Y                          88.7320
## tGravityAcc.mean...Z                          36.4933
## tGravityAcc.std...X                            7.0538
## tGravityAcc.std...Y                            3.2454
## tGravityAcc.std...Z                            3.3840
## tGravityAcc.mad...X                            5.3400
## tGravityAcc.mad...Y                            4.5834
## tGravityAcc.mad...Z                            1.7486
## tGravityAcc.max...X                           71.5647
## tGravityAcc.max...Y                           85.2666
## tGravityAcc.max...Z                           42.7381
## tGravityAcc.min...X                           89.2070
## tGravityAcc.min...Y                           85.9245
## tGravityAcc.min...Z                           28.4641
## tGravityAcc.sma..                             19.7562
## tGravityAcc.energy...X                       121.4364
## tGravityAcc.energy...Y                        73.7145
## tGravityAcc.energy...Z                        30.5691
## tGravityAcc.iqr...X                            5.7279
## tGravityAcc.iqr...Y                            1.8304
## tGravityAcc.iqr...Z                            1.4338
## tGravityAcc.entropy...X                       10.0681
## tGravityAcc.entropy...Y                       26.6120
## tGravityAcc.entropy...Z                        4.6974
## tGravityAcc.arCoeff...X.1                     31.9407
## tGravityAcc.arCoeff...X.2                     26.5633
## tGravityAcc.arCoeff...X.3                     19.0119
## tGravityAcc.arCoeff...X.4                     20.8753
## tGravityAcc.arCoeff...Y.1                     20.7001
## tGravityAcc.arCoeff...Y.2                     20.4852
## tGravityAcc.arCoeff...Y.3                     19.5569
## tGravityAcc.arCoeff...Y.4                     14.5265
## tGravityAcc.arCoeff...Z.1                     27.4809
## tGravityAcc.arCoeff...Z.2                     24.3179
## tGravityAcc.arCoeff...Z.3                     17.9467
## tGravityAcc.arCoeff...Z.4                     14.8817
## tGravityAcc.correlation...X.Y                 10.9755
## tGravityAcc.correlation...X.Z                  4.3606
## tGravityAcc.correlation...Y.Z                  8.1992
## tBodyAccJerk.mean...X                          0.8784
## tBodyAccJerk.mean...Y                          0.6737
## tBodyAccJerk.mean...Z                          0.5923
## tBodyAccJerk.std...X                          25.0709
## tBodyAccJerk.std...Y                           7.1628
## tBodyAccJerk.std...Z                           1.2239
## tBodyAccJerk.mad...X                          18.0024
## tBodyAccJerk.mad...Y                          14.9650
## tBodyAccJerk.mad...Z                           4.5279
## tBodyAccJerk.max...X                          12.8708
## tBodyAccJerk.max...Y                           1.0055
## tBodyAccJerk.max...Z                           1.9046
## tBodyAccJerk.min...X                           5.6275
## tBodyAccJerk.min...Y                           1.1087
## tBodyAccJerk.min...Z                           1.4042
## tBodyAccJerk.sma..                            24.9226
## tBodyAccJerk.energy...X                       20.6114
## tBodyAccJerk.energy...Y                       14.0192
## tBodyAccJerk.energy...Z                        2.3237
## tBodyAccJerk.iqr...X                          10.3705
## tBodyAccJerk.iqr...Y                          28.2070
## tBodyAccJerk.iqr...Z                           8.6257
## tBodyAccJerk.entropy...X                      12.9315
## tBodyAccJerk.entropy...Y                      17.4155
## tBodyAccJerk.entropy...Z                       2.9285
## tBodyAccJerk.arCoeff...X.1                     0.9806
## tBodyAccJerk.arCoeff...X.2                     0.6675
## tBodyAccJerk.arCoeff...X.3                     1.1773
## tBodyAccJerk.arCoeff...X.4                     1.1724
## tBodyAccJerk.arCoeff...Y.1                     1.0208
## tBodyAccJerk.arCoeff...Y.2                     0.7819
## tBodyAccJerk.arCoeff...Y.3                     0.7267
## tBodyAccJerk.arCoeff...Y.4                     1.6176
## tBodyAccJerk.arCoeff...Z.1                     0.9112
## tBodyAccJerk.arCoeff...Z.2                     0.7905
## tBodyAccJerk.arCoeff...Z.3                     1.0154
## tBodyAccJerk.arCoeff...Z.4                     1.5387
## tBodyAccJerk.correlation...X.Y                 3.0132
## tBodyAccJerk.correlation...X.Z                 2.7044
## tBodyAccJerk.correlation...Y.Z                 2.5604
## tBodyGyro.mean...X                             2.8419
## tBodyGyro.mean...Y                             1.7316
## tBodyGyro.mean...Z                             3.7107
## tBodyGyro.std...X                              7.4680
## tBodyGyro.std...Y                              2.0365
## tBodyGyro.std...Z                              2.6356
## tBodyGyro.mad...X                              6.8088
## tBodyGyro.mad...Y                              2.1964
## tBodyGyro.mad...Z                              3.6601
## tBodyGyro.max...X                              8.8321
## tBodyGyro.max...Y                              1.6295
## tBodyGyro.max...Z                              1.5442
## tBodyGyro.min...X                              6.9035
## tBodyGyro.min...Y                              1.2249
## tBodyGyro.min...Z                              2.7578
## tBodyGyro.sma..                                1.2905
## tBodyGyro.energy...X                           4.3350
## tBodyGyro.energy...Y                           2.3753
## tBodyGyro.energy...Z                           3.8239
## tBodyGyro.iqr...X                              7.6703
## tBodyGyro.iqr...Y                              6.1992
## tBodyGyro.iqr...Z                              5.9085
## tBodyGyro.entropy...X                          6.8902
## tBodyGyro.entropy...Y                          1.7720
## tBodyGyro.entropy...Z                          2.2092
## tBodyGyro.arCoeff...X.1                        2.9600
## tBodyGyro.arCoeff...X.2                        0.7530
## tBodyGyro.arCoeff...X.3                        0.8142
## tBodyGyro.arCoeff...X.4                        1.6668
## tBodyGyro.arCoeff...Y.1                        2.4926
## tBodyGyro.arCoeff...Y.2                        0.8937
## tBodyGyro.arCoeff...Y.3                        0.8393
## tBodyGyro.arCoeff...Y.4                        1.8056
## tBodyGyro.arCoeff...Z.1                        0.8023
## tBodyGyro.arCoeff...Z.2                        0.7378
## tBodyGyro.arCoeff...Z.3                        0.8203
## tBodyGyro.arCoeff...Z.4                        1.0126
## tBodyGyro.correlation...X.Y                    4.4771
## tBodyGyro.correlation...X.Z                    2.9330
## tBodyGyro.correlation...Y.Z                    6.7065
## tBodyGyroJerk.mean...X                         1.0964
## tBodyGyroJerk.mean...Y                         0.5082
## tBodyGyroJerk.mean...Z                         1.3346
## tBodyGyroJerk.std...X                          3.9659
## tBodyGyroJerk.std...Y                          1.3525
## tBodyGyroJerk.std...Z                          1.5869
## tBodyGyroJerk.mad...X                         11.2851
## tBodyGyroJerk.mad...Y                          1.1011
## tBodyGyroJerk.mad...Z                          6.2772
## tBodyGyroJerk.max...X                          2.5825
## tBodyGyroJerk.max...Y                          1.1260
## tBodyGyroJerk.max...Z                          1.2505
## tBodyGyroJerk.min...X                          2.8887
## tBodyGyroJerk.min...Y                          1.4059
## tBodyGyroJerk.min...Z                          1.5198
## tBodyGyroJerk.sma..                            7.3391
## tBodyGyroJerk.energy...X                       5.5013
## tBodyGyroJerk.energy...Y                       1.4000
## tBodyGyroJerk.energy...Z                       3.0816
## tBodyGyroJerk.iqr...X                         17.8642
## tBodyGyroJerk.iqr...Y                          1.1774
## tBodyGyroJerk.iqr...Z                         17.8986
## tBodyGyroJerk.entropy...X                      3.9042
## tBodyGyroJerk.entropy...Y                      1.0967
## tBodyGyroJerk.entropy...Z                      6.2260
## tBodyGyroJerk.arCoeff...X.1                    4.6351
## tBodyGyroJerk.arCoeff...X.2                    2.1559
## tBodyGyroJerk.arCoeff...X.3                    3.2664
## tBodyGyroJerk.arCoeff...X.4                    1.0314
## tBodyGyroJerk.arCoeff...Y.1                    1.3629
## tBodyGyroJerk.arCoeff...Y.2                    0.9224
## tBodyGyroJerk.arCoeff...Y.3                    0.7549
## tBodyGyroJerk.arCoeff...Y.4                    0.7991
## tBodyGyroJerk.arCoeff...Z.1                    1.1004
## tBodyGyroJerk.arCoeff...Z.2                    0.8963
## tBodyGyroJerk.arCoeff...Z.3                    1.0632
## tBodyGyroJerk.arCoeff...Z.4                    1.9724
## tBodyGyroJerk.correlation...X.Y                4.5359
## tBodyGyroJerk.correlation...X.Z                3.4587
## tBodyGyroJerk.correlation...Y.Z                3.6711
## tBodyAccMag.mean..                             2.6461
## tBodyAccMag.std..                             29.9885
## tBodyAccMag.mad..                             20.9002
## tBodyAccMag.max..                             11.3300
## tBodyAccMag.min..                              0.6656
## tBodyAccMag.sma..                              2.6270
## tBodyAccMag.energy..                           3.3750
## tBodyAccMag.iqr..                              3.0046
## tBodyAccMag.entropy..                          0.9033
## tBodyAccMag.arCoeff..1                        16.3352
## tBodyAccMag.arCoeff..2                         8.7470
## tBodyAccMag.arCoeff..3                         1.0343
## tBodyAccMag.arCoeff..4                         0.8088
## tGravityAccMag.mean..                          4.5742
## tGravityAccMag.std..                          24.1533
## tGravityAccMag.mad..                          25.3043
## tGravityAccMag.max..                           9.6836
## tGravityAccMag.min..                           0.6260
## tGravityAccMag.sma..                           2.8269
## tGravityAccMag.energy..                        9.8386
## tGravityAccMag.iqr..                           2.2327
## tGravityAccMag.entropy..                       0.7977
## tGravityAccMag.arCoeff..1                     15.0238
## tGravityAccMag.arCoeff..2                      4.9431
## tGravityAccMag.arCoeff..3                      0.9631
## tGravityAccMag.arCoeff..4                      1.1317
## tBodyAccJerkMag.mean..                        13.1287
## tBodyAccJerkMag.std..                          9.7966
## tBodyAccJerkMag.mad..                         14.9144
## tBodyAccJerkMag.max..                          2.3884
## tBodyAccJerkMag.min..                          0.5559
## tBodyAccJerkMag.sma..                          8.8469
## tBodyAccJerkMag.energy..                      11.1628
## tBodyAccJerkMag.iqr..                         19.1939
## tBodyAccJerkMag.entropy..                     13.5533
## tBodyAccJerkMag.arCoeff..1                     0.9467
## tBodyAccJerkMag.arCoeff..2                     1.0217
## tBodyAccJerkMag.arCoeff..3                     0.9866
## tBodyAccJerkMag.arCoeff..4                     0.7915
## tBodyGyroMag.mean..                            1.1335
## tBodyGyroMag.std..                             1.1103
## tBodyGyroMag.mad..                             0.9415
## tBodyGyroMag.max..                             0.8830
## tBodyGyroMag.min..                             1.6474
## tBodyGyroMag.sma..                             1.3903
## tBodyGyroMag.energy..                          1.1461
## tBodyGyroMag.iqr..                             1.0503
## tBodyGyroMag.entropy..                         1.4251
## tBodyGyroMag.arCoeff..1                        2.9498
## tBodyGyroMag.arCoeff..2                        1.6998
## tBodyGyroMag.arCoeff..3                        1.2873
## tBodyGyroMag.arCoeff..4                        1.3052
## tBodyGyroJerkMag.mean..                        8.6352
## tBodyGyroJerkMag.std..                         1.1354
## tBodyGyroJerkMag.mad..                         1.3923
## tBodyGyroJerkMag.max..                         0.6690
## tBodyGyroJerkMag.min..                         0.5454
## tBodyGyroJerkMag.sma..                         2.8177
## tBodyGyroJerkMag.energy..                      1.5974
## tBodyGyroJerkMag.iqr..                         1.6339
## tBodyGyroJerkMag.entropy..                     0.9349
## tBodyGyroJerkMag.arCoeff..1                    1.2466
## tBodyGyroJerkMag.arCoeff..2                    1.3237
## tBodyGyroJerkMag.arCoeff..3                    0.9354
## tBodyGyroJerkMag.arCoeff..4                    1.5255
## fBodyAcc.mean...X                             14.9018
## fBodyAcc.mean...Y                              0.8373
## fBodyAcc.mean...Z                              1.1049
## fBodyAcc.std...X                              13.9574
## fBodyAcc.std...Y                               2.6252
## fBodyAcc.std...Z                               2.5916
## fBodyAcc.mad...X                              30.2175
## fBodyAcc.mad...Y                               1.4432
## fBodyAcc.mad...Z                               1.1414
## fBodyAcc.max...X                              10.3852
## fBodyAcc.max...Y                               4.6064
## fBodyAcc.max...Z                               2.0954
## fBodyAcc.min...X                               0.6368
## fBodyAcc.min...Y                               0.4644
## fBodyAcc.min...Z                               0.6605
## fBodyAcc.sma..                                 2.3737
## fBodyAcc.energy...X                           22.3222
## fBodyAcc.energy...Y                            2.4323
## fBodyAcc.energy...Z                            2.1479
## fBodyAcc.iqr...X                               5.5227
## fBodyAcc.iqr...Y                               0.5028
## fBodyAcc.iqr...Z                               0.7084
## fBodyAcc.entropy...X                          17.0177
## fBodyAcc.entropy...Y                           3.5916
## fBodyAcc.entropy...Z                           0.7664
## fBodyAcc.maxInds.X                             1.5142
## fBodyAcc.maxInds.Y                             1.7082
## fBodyAcc.maxInds.Z                             0.5022
## fBodyAcc.meanFreq...X                          3.3136
## fBodyAcc.meanFreq...Y                          3.3642
## fBodyAcc.meanFreq...Z                          6.1856
## fBodyAcc.skewness...X                          6.9885
## fBodyAcc.kurtosis...X                          5.7623
## fBodyAcc.skewness...Y                          2.6161
## fBodyAcc.kurtosis...Y                          2.4931
## fBodyAcc.skewness...Z                          2.0855
## fBodyAcc.kurtosis...Z                          1.6120
## fBodyAcc.bandsEnergy...1.8                    17.0506
## fBodyAcc.bandsEnergy...9.16                    5.0088
## fBodyAcc.bandsEnergy...17.24                   1.2331
## fBodyAcc.bandsEnergy...25.32                   0.9047
## fBodyAcc.bandsEnergy...33.40                   0.9253
## fBodyAcc.bandsEnergy...41.48                   0.7269
## fBodyAcc.bandsEnergy...49.56                   0.5770
## fBodyAcc.bandsEnergy...57.64                   0.6843
## fBodyAcc.bandsEnergy...1.16                   14.3980
## fBodyAcc.bandsEnergy...17.32                   4.3264
## fBodyAcc.bandsEnergy...33.48                   1.5903
## fBodyAcc.bandsEnergy...49.64                   0.6847
## fBodyAcc.bandsEnergy...1.24                   20.1237
## fBodyAcc.bandsEnergy...25.48                   0.9983
## fBodyAcc.bandsEnergy...1.8.1                   6.2865
## fBodyAcc.bandsEnergy...9.16.1                  1.5529
## fBodyAcc.bandsEnergy...17.24.1                 1.3553
## fBodyAcc.bandsEnergy...25.32.1                 0.7137
## fBodyAcc.bandsEnergy...33.40.1                 0.5354
## fBodyAcc.bandsEnergy...41.48.1                 0.6718
## fBodyAcc.bandsEnergy...49.56.1                 0.6227
## fBodyAcc.bandsEnergy...57.64.1                 0.4157
## fBodyAcc.bandsEnergy...1.16.1                  2.2375
## fBodyAcc.bandsEnergy...17.32.1                 1.0476
## fBodyAcc.bandsEnergy...33.48.1                 0.6623
## fBodyAcc.bandsEnergy...49.64.1                 0.6435
## fBodyAcc.bandsEnergy...1.24.1                  2.5375
## fBodyAcc.bandsEnergy...25.48.1                 0.9182
## fBodyAcc.bandsEnergy...1.8.2                   2.8579
## fBodyAcc.bandsEnergy...9.16.2                  0.7679
## fBodyAcc.bandsEnergy...17.24.2                 2.7142
## fBodyAcc.bandsEnergy...25.32.2                 1.1883
## fBodyAcc.bandsEnergy...33.40.2                 0.8127
## fBodyAcc.bandsEnergy...41.48.2                 0.7208
## fBodyAcc.bandsEnergy...49.56.2                 0.4829
## fBodyAcc.bandsEnergy...57.64.2                 0.5770
## fBodyAcc.bandsEnergy...1.16.2                  2.7904
## fBodyAcc.bandsEnergy...17.32.2                 1.8031
## fBodyAcc.bandsEnergy...33.48.2                 0.8112
## fBodyAcc.bandsEnergy...49.64.2                 0.6122
## fBodyAcc.bandsEnergy...1.24.2                  2.0140
## fBodyAcc.bandsEnergy...25.48.2                 1.1441
## fBodyAccJerk.mean...X                         19.0964
## fBodyAccJerk.mean...Y                          9.9682
## fBodyAccJerk.mean...Z                          1.0428
## fBodyAccJerk.std...X                          19.2633
## fBodyAccJerk.std...Y                           8.9307
## fBodyAccJerk.std...Z                           1.6931
## fBodyAccJerk.mad...X                          22.3556
## fBodyAccJerk.mad...Y                           5.5678
## fBodyAccJerk.mad...Z                           1.3415
## fBodyAccJerk.max...X                          19.6810
## fBodyAccJerk.max...Y                           9.3661
## fBodyAccJerk.max...Z                           1.1695
## fBodyAccJerk.min...X                           0.4608
## fBodyAccJerk.min...Y                           0.5145
## fBodyAccJerk.min...Z                           0.5816
## fBodyAccJerk.sma..                             7.0579
## fBodyAccJerk.energy...X                       24.4501
## fBodyAccJerk.energy...Y                       16.2872
## fBodyAccJerk.energy...Z                        1.0232
## fBodyAccJerk.iqr...X                          10.0205
## fBodyAccJerk.iqr...Y                           2.1205
## fBodyAccJerk.iqr...Z                           1.3513
## fBodyAccJerk.entropy...X                      21.7018
## fBodyAccJerk.entropy...Y                       4.8665
## fBodyAccJerk.entropy...Z                       2.2695
## fBodyAccJerk.maxInds.X                         7.3778
## fBodyAccJerk.maxInds.Y                         0.8074
## fBodyAccJerk.maxInds.Z                         3.0882
## fBodyAccJerk.meanFreq...X                      1.0902
## fBodyAccJerk.meanFreq...Y                      0.9469
## fBodyAccJerk.meanFreq...Z                      1.4501
## fBodyAccJerk.skewness...X                      0.9733
## fBodyAccJerk.kurtosis...X                      0.9677
## fBodyAccJerk.skewness...Y                      2.2437
## fBodyAccJerk.kurtosis...Y                      1.5580
## fBodyAccJerk.skewness...Z                      0.9238
## fBodyAccJerk.kurtosis...Z                      0.8411
## fBodyAccJerk.bandsEnergy...1.8                32.4223
## fBodyAccJerk.bandsEnergy...9.16                3.1781
## fBodyAccJerk.bandsEnergy...17.24               3.1782
## fBodyAccJerk.bandsEnergy...25.32               2.7109
## fBodyAccJerk.bandsEnergy...33.40               2.6276
## fBodyAccJerk.bandsEnergy...41.48               1.3127
## fBodyAccJerk.bandsEnergy...49.56               0.6550
## fBodyAccJerk.bandsEnergy...57.64               0.4931
## fBodyAccJerk.bandsEnergy...1.16               37.8304
## fBodyAccJerk.bandsEnergy...17.32               2.5984
## fBodyAccJerk.bandsEnergy...33.48               5.6677
## fBodyAccJerk.bandsEnergy...49.64               0.5685
## fBodyAccJerk.bandsEnergy...1.24               36.6551
## fBodyAccJerk.bandsEnergy...25.48               3.1501
## fBodyAccJerk.bandsEnergy...1.8.1               6.0682
## fBodyAccJerk.bandsEnergy...9.16.1              7.8796
## fBodyAccJerk.bandsEnergy...17.24.1             1.0547
## fBodyAccJerk.bandsEnergy...25.32.1             2.2768
## fBodyAccJerk.bandsEnergy...33.40.1             0.6336
## fBodyAccJerk.bandsEnergy...41.48.1             0.8363
## fBodyAccJerk.bandsEnergy...49.56.1             0.7347
## fBodyAccJerk.bandsEnergy...57.64.1             0.6387
## fBodyAccJerk.bandsEnergy...1.16.1             10.3396
## fBodyAccJerk.bandsEnergy...17.32.1             1.1454
## fBodyAccJerk.bandsEnergy...33.48.1             0.8711
## fBodyAccJerk.bandsEnergy...49.64.1             0.6965
## fBodyAccJerk.bandsEnergy...1.24.1             13.4471
## fBodyAccJerk.bandsEnergy...25.48.1             3.7275
## fBodyAccJerk.bandsEnergy...1.8.2               3.5619
## fBodyAccJerk.bandsEnergy...9.16.2              0.9429
## fBodyAccJerk.bandsEnergy...17.24.2             3.4052
## fBodyAccJerk.bandsEnergy...25.32.2             1.2754
## fBodyAccJerk.bandsEnergy...33.40.2             1.0885
## fBodyAccJerk.bandsEnergy...41.48.2             0.8807
## fBodyAccJerk.bandsEnergy...49.56.2             0.6535
## fBodyAccJerk.bandsEnergy...57.64.2             0.5651
## fBodyAccJerk.bandsEnergy...1.16.2              0.9673
## fBodyAccJerk.bandsEnergy...17.32.2             2.2089
## fBodyAccJerk.bandsEnergy...33.48.2             1.1736
## fBodyAccJerk.bandsEnergy...49.64.2             0.9866
## fBodyAccJerk.bandsEnergy...1.24.2              1.1121
## fBodyAccJerk.bandsEnergy...25.48.2             1.4721
## fBodyGyro.mean...X                             6.8260
## fBodyGyro.mean...Y                             1.4138
## fBodyGyro.mean...Z                             3.1732
## fBodyGyro.std...X                              9.8380
## fBodyGyro.std...Y                              1.7774
## fBodyGyro.std...Z                              3.6849
## fBodyGyro.mad...X                              7.5956
## fBodyGyro.mad...Y                              1.4947
## fBodyGyro.mad...Z                              1.6428
## fBodyGyro.max...X                              7.1758
## fBodyGyro.max...Y                              1.6263
## fBodyGyro.max...Z                              4.1980
## fBodyGyro.min...X                              0.9276
## fBodyGyro.min...Y                              0.6057
## fBodyGyro.min...Z                              1.3907
## fBodyGyro.sma..                                2.4419
## fBodyGyro.energy...X                           7.4445
## fBodyGyro.energy...Y                           1.9849
## fBodyGyro.energy...Z                           2.9561
## fBodyGyro.iqr...X                              1.2783
## fBodyGyro.iqr...Y                              1.2205
## fBodyGyro.iqr...Z                              0.9754
## fBodyGyro.entropy...X                          5.8222
## fBodyGyro.entropy...Y                          1.7771
## fBodyGyro.entropy...Z                          2.2934
## fBodyGyro.maxInds.X                           10.7804
## fBodyGyro.maxInds.Y                            3.4348
## fBodyGyro.maxInds.Z                           16.2432
## fBodyGyro.meanFreq...X                        13.3328
## fBodyGyro.meanFreq...Y                         1.0657
## fBodyGyro.meanFreq...Z                         1.6018
## fBodyGyro.skewness...X                         4.1979
## fBodyGyro.kurtosis...X                         3.5176
## fBodyGyro.skewness...Y                         2.2651
## fBodyGyro.kurtosis...Y                         2.2399
## fBodyGyro.skewness...Z                         2.3854
## fBodyGyro.kurtosis...Z                         2.6785
## fBodyGyro.bandsEnergy...1.8                   10.4891
## fBodyGyro.bandsEnergy...9.16                   5.6543
## fBodyGyro.bandsEnergy...17.24                  1.6626
## fBodyGyro.bandsEnergy...25.32                  1.4147
## fBodyGyro.bandsEnergy...33.40                  0.9863
## fBodyGyro.bandsEnergy...41.48                  1.3378
## fBodyGyro.bandsEnergy...49.56                  0.9646
## fBodyGyro.bandsEnergy...57.64                  1.1906
## fBodyGyro.bandsEnergy...1.16                   8.4701
## fBodyGyro.bandsEnergy...17.32                  1.3879
## fBodyGyro.bandsEnergy...33.48                  1.6017
## fBodyGyro.bandsEnergy...49.64                  1.0844
## fBodyGyro.bandsEnergy...1.24                   8.5628
## fBodyGyro.bandsEnergy...25.48                  1.0040
## fBodyGyro.bandsEnergy...1.8.1                  2.1820
## fBodyGyro.bandsEnergy...9.16.1                 0.7834
## fBodyGyro.bandsEnergy...17.24.1                1.8884
## fBodyGyro.bandsEnergy...25.32.1                1.6447
## fBodyGyro.bandsEnergy...33.40.1                0.7191
## fBodyGyro.bandsEnergy...41.48.1                0.9951
## fBodyGyro.bandsEnergy...49.56.1                0.6062
## fBodyGyro.bandsEnergy...57.64.1                0.7328
## fBodyGyro.bandsEnergy...1.16.1                 1.8948
## fBodyGyro.bandsEnergy...17.32.1                2.5104
## fBodyGyro.bandsEnergy...33.48.1                0.9346
## fBodyGyro.bandsEnergy...49.64.1                0.6619
## fBodyGyro.bandsEnergy...1.24.1                 2.3500
## fBodyGyro.bandsEnergy...25.48.1                1.5428
## fBodyGyro.bandsEnergy...1.8.2                  2.7494
## fBodyGyro.bandsEnergy...9.16.2                 5.5552
## fBodyGyro.bandsEnergy...17.24.2                1.6577
## fBodyGyro.bandsEnergy...25.32.2                1.7208
## fBodyGyro.bandsEnergy...33.40.2                0.7626
## fBodyGyro.bandsEnergy...41.48.2                1.0425
## fBodyGyro.bandsEnergy...49.56.2                1.1201
## fBodyGyro.bandsEnergy...57.64.2                1.2452
## fBodyGyro.bandsEnergy...1.16.2                 3.9475
## fBodyGyro.bandsEnergy...17.32.2                2.6340
## fBodyGyro.bandsEnergy...33.48.2                1.2711
## fBodyGyro.bandsEnergy...49.64.2                1.4413
## fBodyGyro.bandsEnergy...1.24.2                 2.3043
## fBodyGyro.bandsEnergy...25.48.2                1.2892
## fBodyAccMag.mean..                            13.7269
## fBodyAccMag.std..                             20.8696
## fBodyAccMag.mad..                             25.6626
## fBodyAccMag.max..                              6.1840
## fBodyAccMag.min..                              0.6504
## fBodyAccMag.sma..                             20.9204
## fBodyAccMag.energy..                          31.6260
## fBodyAccMag.iqr..                              1.9474
## fBodyAccMag.entropy..                          5.9728
## fBodyAccMag.maxInds                            1.2791
## fBodyAccMag.meanFreq..                         8.1158
## fBodyAccMag.skewness..                         0.7831
## fBodyAccMag.kurtosis..                         0.8390
## fBodyBodyAccJerkMag.mean..                     6.0361
## fBodyBodyAccJerkMag.std..                     12.4331
## fBodyBodyAccJerkMag.mad..                      6.3689
## fBodyBodyAccJerkMag.max..                     13.6278
## fBodyBodyAccJerkMag.min..                      0.6326
## fBodyBodyAccJerkMag.sma..                     10.2037
## fBodyBodyAccJerkMag.energy..                   5.1774
## fBodyBodyAccJerkMag.iqr..                      2.1316
## fBodyBodyAccJerkMag.entropy..                  0.4845
## fBodyBodyAccJerkMag.maxInds                    0.6242
## fBodyBodyAccJerkMag.meanFreq..                 0.9763
## fBodyBodyAccJerkMag.skewness..                 3.2312
## fBodyBodyAccJerkMag.kurtosis..                 4.1810
## fBodyBodyGyroMag.mean..                        0.8843
## fBodyBodyGyroMag.std..                         0.9464
## fBodyBodyGyroMag.mad..                         0.8911
## fBodyBodyGyroMag.max..                         0.8526
## fBodyBodyGyroMag.min..                         0.7545
## fBodyBodyGyroMag.sma..                         0.9577
## fBodyBodyGyroMag.energy..                      0.8241
## fBodyBodyGyroMag.iqr..                         0.8756
## fBodyBodyGyroMag.entropy..                     0.7778
## fBodyBodyGyroMag.maxInds                       3.5601
## fBodyBodyGyroMag.meanFreq..                    4.5897
## fBodyBodyGyroMag.skewness..                    1.4223
## fBodyBodyGyroMag.kurtosis..                    1.6187
## fBodyBodyGyroJerkMag.mean..                    0.9482
## fBodyBodyGyroJerkMag.std..                     3.6777
## fBodyBodyGyroJerkMag.mad..                     1.2074
## fBodyBodyGyroJerkMag.max..                     4.1060
## fBodyBodyGyroJerkMag.min..                     0.5343
## fBodyBodyGyroJerkMag.sma..                     0.7079
## fBodyBodyGyroJerkMag.energy..                  1.1212
## fBodyBodyGyroJerkMag.iqr..                     0.6684
## fBodyBodyGyroJerkMag.entropy..                 0.6877
## fBodyBodyGyroJerkMag.maxInds                   0.8334
## fBodyBodyGyroJerkMag.meanFreq..                1.2534
## fBodyBodyGyroJerkMag.skewness..                2.3320
## fBodyBodyGyroJerkMag.kurtosis..                2.0582
## angle.tBodyAccMean.gravity.                    0.5810
## angle.tBodyAccJerkMean..gravityMean.           0.4699
## angle.tBodyGyroMean.gravityMean.               2.4040
## angle.tBodyGyroJerkMean.gravityMean.           1.2811
## angle.X.gravityMean.                         106.7852
## angle.Y.gravityMean.                         102.0760
## angle.Z.gravityMean.                          41.6442
## subject                                        3.7524
```

```r
par(mfrow = c(1, 1))
varImpPlot(train.rf, main = "Importance Plot", cex = 0.7)
```

![plot of chunk unnamed-chunk-6](figure/unnamed-chunk-6.png) 

```r
getTree(train.rf, k = 1)
```

```
##     left daughter right daughter split var split point status prediction
## 1               2              3       102   -0.868986      1          0
## 2               4              5        59   -0.615429      1          0
## 3               6              7       216   -0.181375      1          0
## 4               8              9       130   -0.883964      1          0
## 5              10             11       470   -0.999976      1          0
## 6              12             13        71    0.328722      1          0
## 7              14             15       457   -0.070231      1          0
## 8              16             17       345   -0.997205      1          0
## 9              18             19       452   -0.084180      1          0
## 10             20             21       132   -0.752320      1          0
## 11             22             23        66   -0.997548      1          0
## 12             24             25       513    0.057699      1          0
## 13             26             27        42   -0.161406      1          0
## 14             28             29        90   -0.366236      1          0
## 15             30             31        55    0.038989      1          0
## 16             32             33       244   -0.997459      1          0
## 17             34             35       553   -0.937878      1          0
## 18             36             37       150   -0.375917      1          0
## 19             38             39       125   -0.992912      1          0
## 20             40             41        57   -0.722078      1          0
## 21             42             43       117    0.333365      1          0
## 22              0              0         0    0.000000     -1          2
## 23             44             45        41    0.114203      1          0
## 24             46             47       504   -0.335389      1          0
## 25             48             49        51   -0.393227      1          0
## 26             50             51        66   -0.526252      1          0
## 27             52             53        55   -0.316464      1          0
## 28             54             55       560    0.282933      1          0
## 29             56             57       419   -0.969648      1          0
## 30             58             59        38   -0.628479      1          0
## 31              0              0         0    0.000000     -1          5
## 32              0              0         0    0.000000     -1          2
## 33             60             61       244   -0.988387      1          0
## 34              0              0         0    0.000000     -1          3
## 35             62             63       178   -0.999989      1          0
## 36             64             65        54   -0.133760      1          0
## 37             66             67        57   -0.260492      1          0
## 38             68             69       540    0.158691      1          0
## 39             70             71        64   -0.966003      1          0
## 40              0              0         0    0.000000     -1          1
## 41              0              0         0    0.000000     -1          2
## 42              0              0         0    0.000000     -1          2
## 43              0              0         0    0.000000     -1          1
## 44              0              0         0    0.000000     -1          1
## 45             72             73       145   -0.663281      1          0
## 46             74             75        55   -0.484943      1          0
## 47             76             77       131   -0.561837      1          0
## 48             78             79       202   -0.347401      1          0
## 49             80             81       396   -0.391245      1          0
## 50             82             83        23    0.225709      1          0
## 51             84             85       373   -0.268065      1          0
## 52              0              0         0    0.000000     -1          6
## 53             86             87       245   -0.284196      1          0
## 54             88             89       560   -0.075006      1          0
## 55              0              0         0    0.000000     -1          6
## 56             90             91       350   -0.686589      1          0
## 57             92             93        66   -0.208368      1          0
## 58              0              0         0    0.000000     -1          5
## 59              0              0         0    0.000000     -1          6
## 60             94             95       424   -0.996607      1          0
## 61              0              0         0    0.000000     -1          2
## 62             96             97       259   -0.999994      1          0
## 63             98             99       504   -0.477606      1          0
## 64            100            101        60   -0.682358      1          0
## 65            102            103        51    0.642901      1          0
## 66              0              0         0    0.000000     -1          1
## 67            104            105       123    0.202355      1          0
## 68            106            107       424   -0.995687      1          0
## 69              0              0         0    0.000000     -1          2
## 70            108            109        54   -0.070803      1          0
## 71            110            111       314   -0.998261      1          0
## 72              0              0         0    0.000000     -1          3
## 73              0              0         0    0.000000     -1          2
## 74              0              0         0    0.000000     -1          6
## 75            112            113        66   -0.626233      1          0
## 76              0              0         0    0.000000     -1          5
## 77            114            115       189    0.464073      1          0
## 78            116            117       531   -0.544984      1          0
## 79              0              0         0    0.000000     -1          6
## 80            118            119       170   -0.784699      1          0
## 81            120            121        42   -0.296169      1          0
## 82            122            123       385   -0.793092      1          0
## 83            124            125        90   -0.084529      1          0
## 84            126            127       356   -0.679768      1          0
## 85            128            129       506   -0.457464      1          0
## 86            130            131       211    0.269193      1          0
## 87            132            133       560    0.162913      1          0
## 88              0              0         0    0.000000     -1          1
## 89            134            135        22   -0.065016      1          0
## 90              0              0         0    0.000000     -1          5
## 91              0              0         0    0.000000     -1          6
## 92            136            137       466   -0.461864      1          0
## 93            138            139        25    0.311190      1          0
## 94            140            141       330   -0.999853      1          0
## 95            142            143       107   -0.135128      1          0
## 96              0              0         0    0.000000     -1          2
## 97            144            145       446   -0.860285      1          0
## 98            146            147        47   -0.999655      1          0
## 99              0              0         0    0.000000     -1          1
## 100             0              0         0    0.000000     -1          3
## 101             0              0         0    0.000000     -1          2
## 102           148            149       119   -0.399464      1          0
## 103             0              0         0    0.000000     -1          1
## 104           150            151        36   -0.039583      1          0
## 105             0              0         0    0.000000     -1          2
## 106             0              0         0    0.000000     -1          2
## 107           152            153       201   -0.985454      1          0
## 108           154            155       430   -0.993548      1          0
## 109           156            157        72    0.131980      1          0
## 110           158            159        53    0.206741      1          0
## 111           160            161        56    0.041710      1          0
## 112           162            163       220   -0.700675      1          0
## 113           164            165       457    0.273445      1          0
## 114             0              0         0    0.000000     -1          6
## 115             0              0         0    0.000000     -1          4
## 116             0              0         0    0.000000     -1          6
## 117             0              0         0    0.000000     -1          4
## 118           166            167       353   -0.753492      1          0
## 119           168            169       126    0.517489      1          0
## 120             0              0         0    0.000000     -1          6
## 121           170            171       384   -0.344329      1          0
## 122           172            173       146   -0.416611      1          0
## 123           174            175       305   -0.846148      1          0
## 124           176            177       183    0.722470      1          0
## 125             0              0         0    0.000000     -1          5
## 126             0              0         0    0.000000     -1          6
## 127           178            179       509   -0.818248      1          0
## 128             0              0         0    0.000000     -1          4
## 129             0              0         0    0.000000     -1          6
## 130           180            181       341   -0.848200      1          0
## 131           182            183       146   -0.403308      1          0
## 132           184            185       304   -0.672194      1          0
## 133           186            187        73    0.612342      1          0
## 134             0              0         0    0.000000     -1          5
## 135           188            189        73    0.155110      1          0
## 136           190            191       236   -0.700097      1          0
## 137           192            193       505    0.173468      1          0
## 138             0              0         0    0.000000     -1          4
## 139             0              0         0    0.000000     -1          5
## 140             0              0         0    0.000000     -1          2
## 141           194            195       259   -0.999989      1          0
## 142             0              0         0    0.000000     -1          2
## 143             0              0         0    0.000000     -1          3
## 144           196            197       390   -0.999985      1          0
## 145             0              0         0    0.000000     -1          3
## 146             0              0         0    0.000000     -1          1
## 147           198            199       192    0.637184      1          0
## 148           200            201       452   -0.281487      1          0
## 149           202            203       374    0.086094      1          0
## 150           204            205        56   -0.467198      1          0
## 151           206            207        78   -0.995156      1          0
## 152           208            209        43    0.141753      1          0
## 153             0              0         0    0.000000     -1          1
## 154           210            211        92   -0.996979      1          0
## 155           212            213       133    0.845394      1          0
## 156           214            215       559    0.066650      1          0
## 157           216            217       248   -0.242697      1          0
## 158             0              0         0    0.000000     -1          1
## 159           218            219       513   -0.497513      1          0
## 160           220            221        42    0.448578      1          0
## 161             0              0         0    0.000000     -1          2
## 162           222            223       235    0.534137      1          0
## 163           224            225       481   -0.918049      1          0
## 164           226            227       408   -0.822128      1          0
## 165             0              0         0    0.000000     -1          6
## 166             0              0         0    0.000000     -1          1
## 167             0              0         0    0.000000     -1          6
## 168           228            229       527   -0.667063      1          0
## 169             0              0         0    0.000000     -1          6
## 170           230            231       362   -0.575794      1          0
## 171             0              0         0    0.000000     -1          5
## 172           232            233       416   -0.839447      1          0
## 173           234            235       189    0.107867      1          0
## 174             0              0         0    0.000000     -1          6
## 175             0              0         0    0.000000     -1          5
## 176           236            237       127    0.249424      1          0
## 177           238            239       320   -0.880161      1          0
## 178             0              0         0    0.000000     -1          4
## 179           240            241       302   -0.569810      1          0
## 180             0              0         0    0.000000     -1          4
## 181             0              0         0    0.000000     -1          5
## 182           242            243        49   -0.875406      1          0
## 183           244            245       418   -0.894623      1          0
## 184             0              0         0    0.000000     -1          5
## 185             0              0         0    0.000000     -1          4
## 186             0              0         0    0.000000     -1          4
## 187             0              0         0    0.000000     -1          6
## 188             0              0         0    0.000000     -1          4
## 189             0              0         0    0.000000     -1          6
## 190             0              0         0    0.000000     -1          6
## 191           246            247       280   -0.997072      1          0
## 192             0              0         0    0.000000     -1          4
## 193             0              0         0    0.000000     -1          5
## 194             0              0         0    0.000000     -1          3
## 195             0              0         0    0.000000     -1          1
## 196           248            249        27   -0.063441      1          0
## 197           250            251       331   -0.999944      1          0
## 198           252            253       377   -0.496172      1          0
## 199             0              0         0    0.000000     -1          1
## 200             0              0         0    0.000000     -1          3
## 201           254            255       360   -0.939076      1          0
## 202           256            257       535   -0.848830      1          0
## 203             0              0         0    0.000000     -1          3
## 204           258            259       462   -0.999259      1          0
## 205           260            261        50    0.726838      1          0
## 206             0              0         0    0.000000     -1          2
## 207           262            263       483   -0.979937      1          0
## 208             0              0         0    0.000000     -1          3
## 209           264            265       335   -0.999777      1          0
## 210             0              0         0    0.000000     -1          3
## 211           266            267       502   -0.999987      1          0
## 212           268            269       308   -0.999968      1          0
## 213           270            271       386   -0.999940      1          0
## 214           272            273       493   -0.999167      1          0
## 215             0              0         0    0.000000     -1          1
## 216             0              0         0    0.000000     -1          2
## 217             0              0         0    0.000000     -1          1
## 218             0              0         0    0.000000     -1          3
## 219           274            275       138   -0.999927      1          0
## 220             0              0         0    0.000000     -1          3
## 221             0              0         0    0.000000     -1          1
## 222             0              0         0    0.000000     -1          4
## 223             0              0         0    0.000000     -1          5
## 224             0              0         0    0.000000     -1          6
## 225             0              0         0    0.000000     -1          4
## 226             0              0         0    0.000000     -1          6
## 227           276            277       471   -0.870844      1          0
## 228             0              0         0    0.000000     -1          6
## 229           278            279        25   -0.234564      1          0
## 230             0              0         0    0.000000     -1          6
## 231             0              0         0    0.000000     -1          4
## 232             0              0         0    0.000000     -1          6
## 233           280            281       560    0.295641      1          0
## 234             0              0         0    0.000000     -1          6
## 235             0              0         0    0.000000     -1          4
## 236             0              0         0    0.000000     -1          6
## 237             0              0         0    0.000000     -1          4
## 238             0              0         0    0.000000     -1          4
## 239             0              0         0    0.000000     -1          6
## 240             0              0         0    0.000000     -1          5
## 241             0              0         0    0.000000     -1          6
## 242           282            283        40    0.439770      1          0
## 243           284            285       390   -0.952158      1          0
## 244           286            287       136   -0.429210      1          0
## 245             0              0         0    0.000000     -1          4
## 246             0              0         0    0.000000     -1          6
## 247           288            289       559   -0.448093      1          0
## 248             0              0         0    0.000000     -1          3
## 249             0              0         0    0.000000     -1          2
## 250             0              0         0    0.000000     -1          3
## 251           290            291        42   -0.212143      1          0
## 252           292            293       263   -0.681586      1          0
## 253             0              0         0    0.000000     -1          3
## 254             0              0         0    0.000000     -1          3
## 255             0              0         0    0.000000     -1          2
## 256           294            295       552    0.245708      1          0
## 257           296            297       449   -0.966667      1          0
## 258           298            299       227   -0.994747      1          0
## 259             0              0         0    0.000000     -1          3
## 260             0              0         0    0.000000     -1          2
## 261           300            301       199    0.377741      1          0
## 262           302            303       320   -0.999955      1          0
## 263             0              0         0    0.000000     -1          2
## 264             0              0         0    0.000000     -1          3
## 265             0              0         0    0.000000     -1          2
## 266             0              0         0    0.000000     -1          3
## 267             0              0         0    0.000000     -1          2
## 268             0              0         0    0.000000     -1          2
## 269           304            305       142   -0.996382      1          0
## 270             0              0         0    0.000000     -1          3
## 271             0              0         0    0.000000     -1          2
## 272           306            307       191    0.276237      1          0
## 273           308            309       510   -0.958830      1          0
## 274           310            311        80   -0.286535      1          0
## 275           312            313        50    0.903147      1          0
## 276             0              0         0    0.000000     -1          4
## 277           314            315       114    0.113679      1          0
## 278             0              0         0    0.000000     -1          5
## 279           316            317       449   -0.966667      1          0
## 280             0              0         0    0.000000     -1          4
## 281             0              0         0    0.000000     -1          6
## 282             0              0         0    0.000000     -1          5
## 283             0              0         0    0.000000     -1          4
## 284             0              0         0    0.000000     -1          1
## 285             0              0         0    0.000000     -1          6
## 286             0              0         0    0.000000     -1          1
## 287             0              0         0    0.000000     -1          2
## 288           318            319       553    0.232131      1          0
## 289             0              0         0    0.000000     -1          6
## 290             0              0         0    0.000000     -1          3
## 291             0              0         0    0.000000     -1          2
## 292             0              0         0    0.000000     -1          1
## 293           320            321       558    0.832396      1          0
## 294           322            323       195   -0.313396      1          0
## 295             0              0         0    0.000000     -1          3
## 296             0              0         0    0.000000     -1          3
## 297             0              0         0    0.000000     -1          2
## 298             0              0         0    0.000000     -1          3
## 299             0              0         0    0.000000     -1          2
## 300           324            325       561   -0.092384      1          0
## 301           326            327       415   -0.998043      1          0
## 302           328            329       275   -0.997808      1          0
## 303           330            331        23   -0.926093      1          0
## 304             0              0         0    0.000000     -1          2
## 305           332            333       449   -0.033333      1          0
## 306           334            335       392   -0.999942      1          0
## 307           336            337       150   -0.231706      1          0
## 308             0              0         0    0.000000     -1          2
## 309             0              0         0    0.000000     -1          3
## 310             0              0         0    0.000000     -1          3
## 311             0              0         0    0.000000     -1          2
## 312           338            339       301    0.444536      1          0
## 313             0              0         0    0.000000     -1          3
## 314             0              0         0    0.000000     -1          4
## 315             0              0         0    0.000000     -1          6
## 316           340            341       201   -0.159658      1          0
## 317           342            343       480   -0.457038      1          0
## 318           344            345       527   -0.724910      1          0
## 319           346            347       409   -0.753024      1          0
## 320           348            349       555   -0.758233      1          0
## 321             0              0         0    0.000000     -1          3
## 322             0              0         0    0.000000     -1          3
## 323             0              0         0    0.000000     -1          2
## 324           350            351       483   -0.950089      1          0
## 325           352            353       398   -0.999911      1          0
## 326             0              0         0    0.000000     -1          2
## 327             0              0         0    0.000000     -1          3
## 328             0              0         0    0.000000     -1          3
## 329             0              0         0    0.000000     -1          2
## 330             0              0         0    0.000000     -1          2
## 331           354            355       523   -0.983342      1          0
## 332           356            357       533   -0.999635      1          0
## 333             0              0         0    0.000000     -1          2
## 334           358            359       140   -0.993203      1          0
## 335             0              0         0    0.000000     -1          2
## 336             0              0         0    0.000000     -1          2
## 337           360            361       350   -0.982937      1          0
## 338           362            363       480   -0.999985      1          0
## 339           364            365       401   -0.995702      1          0
## 340             0              0         0    0.000000     -1          4
## 341             0              0         0    0.000000     -1          5
## 342           366            367       288    0.836881      1          0
## 343             0              0         0    0.000000     -1          6
## 344             0              0         0    0.000000     -1          6
## 345           368            369       237    0.680642      1          0
## 346             0              0         0    0.000000     -1          6
## 347             0              0         0    0.000000     -1          5
## 348             0              0         0    0.000000     -1          1
## 349           370            371        41    0.146379      1          0
## 350             0              0         0    0.000000     -1          2
## 351             0              0         0    0.000000     -1          6
## 352             0              0         0    0.000000     -1          2
## 353             0              0         0    0.000000     -1          3
## 354           372            373       326   -0.999882      1          0
## 355           374            375       127   -0.981981      1          0
## 356             0              0         0    0.000000     -1          2
## 357           376            377        55   -0.391796      1          0
## 358             0              0         0    0.000000     -1          2
## 359             0              0         0    0.000000     -1          3
## 360             0              0         0    0.000000     -1          3
## 361           378            379       298   -0.968277      1          0
## 362           380            381       457   -0.212158      1          0
## 363             0              0         0    0.000000     -1          2
## 364           382            383       118    0.173980      1          0
## 365             0              0         0    0.000000     -1          3
## 366           384            385       156    0.226599      1          0
## 367             0              0         0    0.000000     -1          6
## 368           386            387       220   -0.492792      1          0
## 369           388            389       349   -0.043679      1          0
## 370             0              0         0    0.000000     -1          1
## 371           390            391        54   -0.140691      1          0
## 372           392            393        64   -0.932296      1          0
## 373           394            395       560    0.038546      1          0
## 374           396            397       262    0.248096      1          0
## 375           398            399       352   -0.985814      1          0
## 376           400            401       335   -0.999773      1          0
## 377           402            403       158    0.651604      1          0
## 378             0              0         0    0.000000     -1          3
## 379             0              0         0    0.000000     -1          2
## 380             0              0         0    0.000000     -1          3
## 381             0              0         0    0.000000     -1          2
## 382           404            405       434   -0.987036      1          0
## 383           406            407       480   -0.999625      1          0
## 384             0              0         0    0.000000     -1          4
## 385           408            409       173    0.431461      1          0
## 386           410            411       177   -0.712087      1          0
## 387             0              0         0    0.000000     -1          5
## 388             0              0         0    0.000000     -1          5
## 389             0              0         0    0.000000     -1          6
## 390           412            413        92   -0.987198      1          0
## 391           414            415       186   -0.428604      1          0
## 392             0              0         0    0.000000     -1          3
## 393             0              0         0    0.000000     -1          2
## 394             0              0         0    0.000000     -1          2
## 395           416            417       493   -0.999983      1          0
## 396           418            419       350   -0.986367      1          0
## 397             0              0         0    0.000000     -1          2
## 398             0              0         0    0.000000     -1          2
## 399           420            421       249   -0.584902      1          0
## 400             0              0         0    0.000000     -1          2
## 401             0              0         0    0.000000     -1          3
## 402           422            423        58   -0.989655      1          0
## 403             0              0         0    0.000000     -1          2
## 404             0              0         0    0.000000     -1          3
## 405             0              0         0    0.000000     -1          2
## 406             0              0         0    0.000000     -1          3
## 407             0              0         0    0.000000     -1          2
## 408             0              0         0    0.000000     -1          5
## 409             0              0         0    0.000000     -1          4
## 410             0              0         0    0.000000     -1          5
## 411             0              0         0    0.000000     -1          4
## 412             0              0         0    0.000000     -1          3
## 413             0              0         0    0.000000     -1          2
## 414             0              0         0    0.000000     -1          3
## 415           424            425       379   -0.975779      1          0
## 416           426            427        32    0.059422      1          0
## 417             0              0         0    0.000000     -1          3
## 418             0              0         0    0.000000     -1          2
## 419             0              0         0    0.000000     -1          3
## 420           428            429       115    0.007891      1          0
## 421           430            431       395   -0.999858      1          0
## 422           432            433       184   -0.304538      1          0
## 423             0              0         0    0.000000     -1          3
## 424           434            435       399   -0.999878      1          0
## 425             0              0         0    0.000000     -1          2
## 426             0              0         0    0.000000     -1          2
## 427             0              0         0    0.000000     -1          3
## 428             0              0         0    0.000000     -1          3
## 429             0              0         0    0.000000     -1          2
## 430           436            437       345   -0.991303      1          0
## 431             0              0         0    0.000000     -1          3
## 432             0              0         0    0.000000     -1          3
## 433             0              0         0    0.000000     -1          2
## 434             0              0         0    0.000000     -1          3
## 435             0              0         0    0.000000     -1          2
## 436             0              0         0    0.000000     -1          3
## 437             0              0         0    0.000000     -1          2
```

```r
table(validateSet$activity, predict(train.rf, validateSet[, -563]))
```

```
##           
##            laying sitting standing walk walkdown walkup
##   laying      277       0        0    0        0      0
##   sitting       0     252        0    0        0      0
##   standing      0       0      237    0        0      0
##   walk          0       0        0  212        2      4
##   walkdown      0       0        0    0      174      0
##   walkup        0       0        0    0       10    189
```


Cross-validate
--------------

Apply to test set
-----------------

```r
table(testSet$activity, predict(train.rf, testSet[, -563]))
```

```
##           
##            laying sitting standing walk walkdown walkup
##   laying      293       0        0    0        0      0
##   sitting       0     225       39    0        0      0
##   standing      0      26      257    0        0      0
##   walk          0       0        0  228        0      1
##   walkdown      0       0        0    1      195      4
##   walkup        0       0        0    1        6    209
```


### Refine if validation
