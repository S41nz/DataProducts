Developing Data Products - Final Presentation
========================================================
author: Pablo Sainz 
date: July 22nd 2019
autosize: true

Overview
========================================================

The main goals to be addressed by the DataProductsApp are the following ones:

- Create a simple application to apply the knowledge acquired during the course for R application development.
- Illustrate in an interactive manner the correlation between vehicle weight and its corresponding fuel consumption efficiency.
- Make a comparison between two relative simple models using linear regression.

Click on the link to try out: <https://s41nz.shinyapps.io/DataProductsApp/>.

Target Data
========================================================


```r
names(mtcars)
```

```
 [1] "mpg"  "cyl"  "disp" "hp"   "drat" "wt"   "qsec" "vs"   "am"   "gear"
[11] "carb"
```

```r
head(mtcars)
```

```
                   mpg cyl disp  hp drat    wt  qsec vs am gear carb
Mazda RX4         21.0   6  160 110 3.90 2.620 16.46  0  1    4    4
Mazda RX4 Wag     21.0   6  160 110 3.90 2.875 17.02  0  1    4    4
Datsun 710        22.8   4  108  93 3.85 2.320 18.61  1  1    4    1
Hornet 4 Drive    21.4   6  258 110 3.08 3.215 19.44  1  0    3    1
Hornet Sportabout 18.7   8  360 175 3.15 3.440 17.02  0  0    3    2
Valiant           18.1   6  225 105 2.76 3.460 20.22  1  0    3    1
```

Proposed Models
========================================================


```r
mtcars$mpgsp <- ifelse(mtcars$mpg - 20 > 0,mtcars$mpg-20,0)
# Simplest model (just mpg as predictor)
testModel1 <- lm(wt ~ mpg,data = mtcars)
# More complex one ( user input + mpg as predictor)
testModel2 <- lm(wt ~ mpgsp + mpg, data = mtcars)
```
The application uses both models to plot a comparison with the actual data from the 
database.

========================================================
Thank you : )
