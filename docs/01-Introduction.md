# Understanding the data from a product perspective
## Understanding the products from a chemical and physical point of view

In the following code, we first import the data with the **read.delim2** function, then we print the first rows with the **head** function ; finally we make a summary of the dataset with the **summary** function. All these steps are really important when you begin you analysis. Tentative.


```r
salmon_car <- read.delim2("Salmon_characteristics.txt", 
header=TRUE, row.names=1, comment.char="#",dec=",")
head(salmon_car)
```

```
##              water   lipid    TVBN     TMA    salt  phenol      pH
## prod1_Fr   -0.8644  1.1375 -0.7629 -0.8717 -0.1471 -0.3776  1.5412
## prod2_Fr   -1.1476  0.7036  0.2357  0.3204  0.1626  0.0112  1.2098
## prod3_Fr   -0.4172  0.3378  0.4354  1.2144  0.3174  0.4001  0.3812
## prod4_Scot -0.8147 -0.0961 -0.5632 -0.8717  0.3174 -0.4554  0.2154
## prod5_Ger  -1.6991  0.0366 -0.7629 -0.8717  2.1752 -0.3776 -0.2817
## prod6_Ire  -0.9886  0.9653 -0.7629 -0.8717  0.0077  0.6594  1.0441
##            total.viable.count lactic.flora lactobacilli brochothrix   yeast
## prod1_Fr               0.1112       0.6665       1.1382      0.5461  0.7729
## prod2_Fr               0.4302      -0.4514       0.1290     -0.7559  1.2034
## prod3_Fr               0.8225       0.8725       0.4088      0.6465  0.2875
## prod4_Scot            -0.2432      -1.5861      -1.0624     -0.7559 -1.0340
## prod5_Ger             -1.5584      -1.5861      -1.0624     -0.7559 -1.0340
## prod6_Ire             -2.5977      -1.5861      -1.0624     -0.7559 -1.0340
##            enterobacteriaceae       L       a       b   origin
## prod1_Fr               0.8314  0.9917 -0.6467 -0.4567   France
## prod2_Fr               0.5998  0.8542  0.5297  0.9551   France
## prod3_Fr               0.2524 -0.8548  0.3927  0.2813   France
## prod4_Scot            -1.5793  0.3020  1.7439  3.3236 Scotland
## prod5_Ger             -0.9582 -1.3485  0.7341  0.5485  Germany
## prod6_Ire             -1.5793 -0.4322  0.4016  0.4278  Ireland
```

```r
summary(salmon_car)
```

```
##      water              lipid                 TVBN              TMA            
##  Min.   :-1.69910   Min.   :-2.4628000   Min.   :-1.1623   Min.   :-0.8717000  
##  1st Qu.:-0.85198   1st Qu.:-0.4259750   1st Qu.:-0.7629   1st Qu.:-0.8717000  
##  Median :-0.07435   Median : 0.2159000   Median :-0.3635   Median :-0.2757000  
##  Mean   :-0.00001   Mean   : 0.0000067   Mean   : 0.0000   Mean   : 0.0000033  
##  3rd Qu.: 0.47713   3rd Qu.: 0.5763000   3rd Qu.: 0.4354   3rd Qu.: 0.5439000  
##  Max.   : 2.02730   Max.   : 1.6251000   Max.   : 2.6322   Max.   : 2.4065000  
##       salt             phenol               pH             total.viable.count  
##  Min.   :-2.0049   Min.   :-1.20730   Min.   :-1.7733000   Min.   :-2.5977000  
##  1st Qu.:-0.6115   1st Qu.:-0.65633   1st Qu.:-0.8617500   1st Qu.:-0.3530250  
##  Median : 0.0077   Median :-0.29985   Median :-0.0331500   Median : 0.2699000  
##  Mean   : 0.0000   Mean   : 0.00001   Mean   :-0.0000067   Mean   : 0.0000067  
##  3rd Qu.: 0.3174   3rd Qu.: 0.40010   3rd Qu.: 0.8368750   3rd Qu.: 0.8187750  
##  Max.   : 2.4848   Max.   : 3.45930   Max.   : 2.0384000   Max.   : 1.1384000  
##   lactic.flora         lactobacilli         brochothrix     
##  Min.   :-1.5861000   Min.   :-1.0624000   Min.   :-0.7559  
##  1st Qu.:-0.4710500   1st Qu.:-1.0624000   1st Qu.:-0.7559  
##  Median : 0.3886500   Median : 0.2064500   Median :-0.7559  
##  Mean   : 0.0000033   Mean   :-0.0000067   Mean   : 0.0000  
##  3rd Qu.: 0.8312750   3rd Qu.: 0.9333500   3rd Qu.: 0.8192  
##  Max.   : 1.5327000   Max.   : 1.9639000   Max.   : 2.4632  
##      yeast            enterobacteriaceae       L                 a          
##  Min.   :-1.0340000   Min.   :-1.57930   Min.   :-1.8353   Min.   :-3.9939  
##  1st Qu.:-1.0340000   1st Qu.:-0.65815   1st Qu.:-0.8034   1st Qu.:-0.4152  
##  Median : 0.2608000   Median : 0.04190   Median : 0.1441   Median : 0.2868  
##  Mean   : 0.0000033   Mean   :-0.00001   Mean   : 0.0000   Mean   : 0.0000  
##  3rd Qu.: 0.7537750   3rd Qu.: 0.79060   3rd Qu.: 0.5455   3rd Qu.: 0.5362  
##  Max.   : 2.1072000   Max.   : 1.64720   Max.   : 2.5982   Max.   : 1.7439  
##        b                origin         
##  Min.   :-1.827700   Length:30         
##  1st Qu.:-0.577750   Class :character  
##  Median : 0.073650   Mode  :character  
##  Mean   :-0.000003                     
##  3rd Qu.: 0.388475                     
##  Max.   : 3.323600
```


