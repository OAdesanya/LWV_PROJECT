# LWV ISSUE
OLufemi Adesanya  
July 13, 2016  
### Dataset Import and summary

```r
getwd()
```

```
## [1] "\\\\vrisi01/users$/oadesanya/Documents"
```

```r
LWData <-read.csv("LWV_Data.csv")
LWData1 <- data.frame(LWData)
LWPop <-LWData1[!is.na(LWData1$control),]
head(LWPop, 20)
```

```
##     VOTED2014 Young.Hispanic.Status ID.Number Voter.Status Voted.11.2012
## 39          0               non_y_h      5461            A             1
## 51          0               non_y_h      6832            A             0
## 217         0           non_y_non_h     16298            A             0
## 313         1               non_y_h     20802            A             0
## 370         0           non_y_non_h     23641            A             0
## 374         0           non_y_non_h     23821            A             0
## 406         0           non_y_non_h     25164            A             0
## 432         0           non_y_non_h     27016            A             0
## 450         1           non_y_non_h     28260            A             0
## 455         0           non_y_non_h     28523            A             0
## 465         0           non_y_non_h     28929            A             0
## 487         1               non_y_h     31178            A             0
## 531         0           non_y_non_h     34400            A             0
## 539         0           non_y_non_h     35136            A             0
## 546         1           non_y_non_h     36004            A             0
## 605         0           non_y_non_h     40437            A             0
## 615         0           non_y_non_h     40970            A             0
## 779         0               non_y_h     55715            A             1
## 861         0           non_y_non_h     61902            A             0
## 871         0           non_y_non_h     63126            A             0
##     Voted.Gen..Elec..09.2010 Voted.Gen..Elec..07.2008
## 39                         0                        0
## 51                         0                        0
## 217                        0                        1
## 313                        0                        1
## 370                        1                        0
## 374                        0                        1
## 406                        0                        1
## 432                        1                        0
## 450                        0                        0
## 455                        0                        0
## 465                        0                        0
## 487                        0                        1
## 531                        0                        0
## 539                        0                        1
## 546                        0                        1
## 605                        0                        0
## 615                        0                        0
## 779                        0                        0
## 861                        0                        0
## 871                        0                        0
##     Number.General.Elections Hispanic.Surname Young.Voter Eligible.2012
## 39                         1                1           0             1
## 51                         0                1           0             1
## 217                        1                0           0             1
## 313                        1                1           0             1
## 370                        1                0           0             1
## 374                        1                0           0             1
## 406                        1                0           0             1
## 432                        1                0           0             1
## 450                        0                0           0             1
## 455                        0                0           0             1
## 465                        0                0           0             1
## 487                        1                1           0             1
## 531                        0                0           0             1
## 539                        1                0           0             1
## 546                        1                0           0             1
## 605                        0                0           0             1
## 615                        0                0           0             1
## 779                        1                1           0             1
## 861                        0                0           0             1
## 871                        0                0           0             1
##     Eligible.2010 Eligible.2008 Young.in.2012 Young.in.2010 Young.in.2008
## 39              1             1             0             0             0
## 51              1             1             0             0             0
## 217             1             1             0             0             0
## 313             1             1             0             0             0
## 370             1             1             0             0             0
## 374             1             1             0             0             0
## 406             1             1             0             0             0
## 432             1             1             0             0             0
## 450             1             1             0             0             0
## 455             1             1             0             0             0
## 465             1             1             0             0             0
## 487             1             1             0             0             0
## 531             1             1             0             0             0
## 539             1             1             0             0             0
## 546             1             1             0             0             0
## 605             1             1             0             0             0
## 615             1             1             0             0             0
## 779             1             1             0             0             0
## 861             1             1             0             0             0
## 871             1             1             0             0             0
##       Voter.Category             type    ID control post flyer LOWPROP
## 39      Old Hispanic     Non_y_h_POST  5461       0    1     0       1
## 51      Old Hispanic     Non_y_h_POST  6832       0    1     0       1
## 217 Old Not Hispanic Non_y_non_h_POST 16298       0    1     0       1
## 313     Old Hispanic     Non_y_h_POST 20802       0    1     0       1
## 370 Old Not Hispanic Non_y_non_h_POST 23641       0    1     0       1
## 374 Old Not Hispanic Non_y_non_h_POST 23821       0    1     0       1
## 406 Old Not Hispanic Non_y_non_h_POST 25164       0    1     0       1
## 432 Old Not Hispanic Non_y_non_h_POST 27016       0    1     0       1
## 450 Old Not Hispanic Non_y_non_h_POST 28260       0    1     0       1
## 455 Old Not Hispanic Non_y_non_h_POST 28523       0    1     0       1
## 465 Old Not Hispanic Non_y_non_h_POST 28929       0    1     0       1
## 487     Old Hispanic     Non_y_h_POST 31178       0    1     0       1
## 531 Old Not Hispanic Non_y_non_h_POST 34400       0    1     0       1
## 539 Old Not Hispanic Non_y_non_h_POST 35136       0    1     0       1
## 546 Old Not Hispanic Non_y_non_h_POST 36004       0    1     0       1
## 605 Old Not Hispanic Non_y_non_h_POST 40437       0    1     0       1
## 615 Old Not Hispanic Non_y_non_h_POST 40970       0    1     0       1
## 779     Old Hispanic     Non_y_h_POST 55715       0    1     0       1
## 861 Old Not Hispanic Non_y_non_h_POST 61902       0    1     0       1
## 871 Old Not Hispanic Non_y_non_h_POST 63126       0    1     0       1
##              city   zip U_S__CONGRESS byear
## 39     CARROLLTON 75007            24  1937
## 51     CARROLLTON 75006            24  1911
## 217       GARLAND 75042            32  1922
## 313       GARLAND 75040            32  1938
## 370       GARLAND 75041            32  1911
## 374       GARLAND 75041            32  1927
## 406       GARLAND 75043            32  1926
## 432       GARLAND 75040            32  1928
## 450       GARLAND 75040            32  1944
## 455       GARLAND 75040            32  1931
## 465       GARLAND 75044            32  1941
## 487       GARLAND 75041            32  1911
## 531       GARLAND 75041            32  1911
## 539    RICHARDSON 75081            32  1936
## 546      MESQUITE 75149             5  1939
## 605       GARLAND 75043            32  1938
## 615       GARLAND 75043            32  1911
## 779 GRAND PRAIRIE 75050            33  1944
## 861 GRAND PRAIRIE 75051            33  1954
## 871 GRAND PRAIRIE 75051            33  1909
```

```r
summary(LWPop)
```

```
##    VOTED2014      Young.Hispanic.Status   ID.Number       Voter.Status
##  Min.   :0.0000   non_y_h    :6416      Min.   :   5461   A:24000     
##  1st Qu.:0.0000   non_y_non_h:6499      1st Qu.:3410570               
##  Median :0.0000   y_h        :5584      Median :3870405               
##  Mean   :0.1238   y_non_h    :5501      Mean   :3604325               
##  3rd Qu.:0.0000                         3rd Qu.:4067789               
##  Max.   :1.0000                         Max.   :4216505               
##                                                                       
##  Voted.11.2012    Voted.Gen..Elec..09.2010 Voted.Gen..Elec..07.2008
##  Min.   :0.0000   Min.   :0.000000         Min.   :0.0000          
##  1st Qu.:0.0000   1st Qu.:0.000000         1st Qu.:0.0000          
##  Median :0.0000   Median :0.000000         Median :0.0000          
##  Mean   :0.2317   Mean   :0.009583         Mean   :0.1155          
##  3rd Qu.:0.0000   3rd Qu.:0.000000         3rd Qu.:0.0000          
##  Max.   :1.0000   Max.   :1.000000         Max.   :1.0000          
##                                                                    
##  Number.General.Elections Hispanic.Surname  Young.Voter    
##  Min.   :0.0000           Min.   :0.0      Min.   :0.0000  
##  1st Qu.:0.0000           1st Qu.:0.0      1st Qu.:0.0000  
##  Median :0.0000           Median :0.5      Median :0.0000  
##  Mean   :0.3568           Mean   :0.5      Mean   :0.4619  
##  3rd Qu.:1.0000           3rd Qu.:1.0      3rd Qu.:1.0000  
##  Max.   :1.0000           Max.   :1.0      Max.   :1.0000  
##                                                            
##  Eligible.2012    Eligible.2010    Eligible.2008    Young.in.2012 
##  Min.   :0.0000   Min.   :0.0000   Min.   :0.0000   Min.   :0.00  
##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:0.00  
##  Median :1.0000   Median :1.0000   Median :0.0000   Median :1.00  
##  Mean   :0.7338   Mean   :0.5009   Mean   :0.4216   Mean   :0.54  
##  3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:1.00  
##  Max.   :1.0000   Max.   :1.0000   Max.   :1.0000   Max.   :1.00  
##                                                                   
##  Young.in.2010    Young.in.2008               Voter.Category
##  Min.   :0.0000   Min.   :0.0000   Old Hispanic      :6416  
##  1st Qu.:0.0000   1st Qu.:0.0000   Old Not Hispanic  :6499  
##  Median :1.0000   Median :1.0000   Young Hispanic    :5584  
##  Mean   :0.5756   Mean   :0.6071   Young Not Hispanic:5501  
##  3rd Qu.:1.0000   3rd Qu.:1.0000                            
##  Max.   :1.0000   Max.   :1.0000                            
##                                                             
##                   type             ID             control      
##  Non_y_h_CONTROL    : 2000   Min.   :   5461   Min.   :0.0000  
##  Non_y_h_FLYER      : 2000   1st Qu.:3410570   1st Qu.:0.0000  
##  Non_y_h_POST       : 2000   Median :3870405   Median :0.0000  
##  Non_y_non_h_CONTROL: 2000   Mean   :3604325   Mean   :0.3333  
##  Non_y_non_h_FLYER  : 2000   3rd Qu.:4067789   3rd Qu.:1.0000  
##  Non_y_non_h_POST   : 2000   Max.   :4216505   Max.   :1.0000  
##  (Other)            :12000                                     
##       post            flyer           LOWPROP             city      
##  Min.   :0.0000   Min.   :0.0000   Min.   :1   DALLAS       :12271  
##  1st Qu.:0.0000   1st Qu.:0.0000   1st Qu.:1   GARLAND      : 2190  
##  Median :0.0000   Median :0.0000   Median :1   IRVING       : 1907  
##  Mean   :0.3333   Mean   :0.3333   Mean   :1   MESQUITE     : 1381  
##  3rd Qu.:1.0000   3rd Qu.:1.0000   3rd Qu.:1   GRAND PRAIRIE: 1333  
##  Max.   :1.0000   Max.   :1.0000   Max.   :1   RICHARDSON   :  657  
##                                                (Other)      : 4261  
##       zip        U_S__CONGRESS       byear     
##  Min.   :75001   Min.   : 5.00   Min.   :1908  
##  1st Qu.:75062   1st Qu.:30.00   1st Qu.:1967  
##  Median :75204   Median :30.00   Median :1984  
##  Mean   :75155   Mean   :27.21   Mean   :1977  
##  3rd Qu.:75223   3rd Qu.:32.00   3rd Qu.:1990  
##  Max.   :75254   Max.   :33.00   Max.   :1996  
## 
```
### The first 100 rows from the population shows that majority of the voters are old and non hispanic people. The popluation does not reflect sample representation of young and hispanc voters




### Descriptive statistics

```r
library(pastecs) #descriptive statistics package
```

```
## Warning: package 'pastecs' was built under R version 3.3.1
```

```
## Loading required package: boot
```

```r
options(scipen =  100) #change format display for descriptive statistics
options (digits = 2) #change format display for descriptive statistics
stat.desc(LWPop, basic = F) #Basic Descriptive statistics of the population
```

```
##              VOTED2014 Young.Hispanic.Status      ID.Number Voter.Status
## median          0.0000                    NA      3870405.0           NA
## mean            0.1238                    NA      3604325.4           NA
## SE.mean         0.0021                    NA         4603.4           NA
## CI.mean.0.95    0.0042                    NA         9023.0           NA
## var             0.1085                    NA 508600932920.5           NA
## std.dev         0.3294                    NA       713162.6           NA
## coef.var        2.6600                    NA            0.2           NA
##              Voted.11.2012 Voted.Gen..Elec..09.2010
## median              0.0000                  0.00000
## mean                0.2317                  0.00958
## SE.mean             0.0027                  0.00063
## CI.mean.0.95        0.0053                  0.00123
## var                 0.1780                  0.00949
## std.dev             0.4219                  0.09743
## coef.var            1.8210                 10.16623
##              Voted.Gen..Elec..07.2008 Number.General.Elections
## median                         0.0000                   0.0000
## mean                           0.1155                   0.3568
## SE.mean                        0.0021                   0.0031
## CI.mean.0.95                   0.0040                   0.0061
## var                            0.1022                   0.2295
## std.dev                        0.3196                   0.4791
## coef.var                       2.7674                   1.3427
##              Hispanic.Surname Young.Voter Eligible.2012 Eligible.2010
## median                 0.5000      0.0000        1.0000        1.0000
## mean                   0.5000      0.4619        0.7338        0.5009
## SE.mean                0.0032      0.0032        0.0029        0.0032
## CI.mean.0.95           0.0063      0.0063        0.0056        0.0063
## var                    0.2500      0.2486        0.1954        0.2500
## std.dev                0.5000      0.4986        0.4420        0.5000
## coef.var               1.0000      1.0794        0.6024        0.9983
##              Eligible.2008 Young.in.2012 Young.in.2010 Young.in.2008
## median              0.0000        1.0000        1.0000        1.0000
## mean                0.4216        0.5400        0.5756        0.6071
## SE.mean             0.0032        0.0032        0.0032        0.0032
## CI.mean.0.95        0.0062        0.0063        0.0063        0.0062
## var                 0.2439        0.2484        0.2443        0.2385
## std.dev             0.4938        0.4984        0.4943        0.4884
## coef.var            1.1713        0.9230        0.8586        0.8044
##              Voter.Category type             ID control  post flyer
## median                   NA   NA      3870405.0   0.000 0.000 0.000
## mean                     NA   NA      3604325.4   0.333 0.333 0.333
## SE.mean                  NA   NA         4603.4   0.003 0.003 0.003
## CI.mean.0.95             NA   NA         9023.0   0.006 0.006 0.006
## var                      NA   NA 508600932920.5   0.222 0.222 0.222
## std.dev                  NA   NA       713162.6   0.471 0.471 0.471
## coef.var                 NA   NA            0.2   1.414 1.414 1.414
##              LOWPROP city        zip U_S__CONGRESS     byear
## median             1   NA 75204.0000        30.000 1983.5000
## mean               1   NA 75154.9353        27.211 1977.1323
## SE.mean            0   NA     0.5120         0.057    0.1069
## CI.mean.0.95       0   NA     1.0035         0.111    0.2094
## var                0   NA  6290.8031        77.243  274.0387
## std.dev            0   NA    79.3146         8.789   16.5541
## coef.var           0   NA     0.0011         0.323    0.0084
```
### This shows the count of old and young people included in the population. The result shows more old people constitute the population. 


### Counts of Population

```r
table(LWPop$Young.Hispanic.Status) #to do a count of young voters
```

```
## 
##     non_y_h non_y_non_h         y_h     y_non_h 
##        6416        6499        5584        5501
```

```r
table(LWPop$Young.Voter)  #sum of all young voter compared to old voters
```

```
## 
##     0     1 
## 12915 11085
```

```r
table(LWPop$Voter.Category) #to do a count of young voter
```

```
## 
##       Old Hispanic   Old Not Hispanic     Young Hispanic 
##               6416               6499               5584 
## Young Not Hispanic 
##               5501
```

```r
table(LWPop$control) #sample population for control group
```

```
## 
##     0     1 
## 16000  8000
```

```r
table(LWPop$post) #sample population for post group
```

```
## 
##     0     1 
## 16000  8000
```

```r
table(LWPop$flyer) #sample population for flyer group
```

```
## 
##     0     1 
## 16000  8000
```

```r
table(LWPop$VOTED2014) #number of people who voted from the population of 24000
```

```
## 
##     0     1 
## 21028  2972
```

### Here, we plotted the sample data and the whole data to compare our young and hispanic voters representation.The majority voters in the whole data are non young and non hispanic. This is not a representative of what the researcher will like to perform.

### Plot

```r
plot(LWPop$Young.Hispanic.Status) #Graphical representation to validate Sampling error for sample population
```

![](LWV_Analysis_files/figure-html/unnamed-chunk-4-1.png)<!-- -->

```r
plot(LWData1$Young.Hispanic.Status) #Graphical representation of all population
```

![](LWV_Analysis_files/figure-html/unnamed-chunk-4-2.png)<!-- -->
