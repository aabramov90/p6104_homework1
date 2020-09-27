Homework 1
================
Alexey Abramov

# Setup

``` r
library(tidyverse)
```

    ## ── Attaching packages ────────────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.3.2     ✓ purrr   0.3.4
    ## ✓ tibble  3.0.3     ✓ dplyr   1.0.2
    ## ✓ tidyr   1.1.2     ✓ stringr 1.4.0
    ## ✓ readr   1.3.1     ✓ forcats 0.5.0

    ## ── Conflicts ───────────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)
```

# Problem 1

``` r
problem1_df = 
  tibble(
    women_sample = c(1:11),
    fe_level = c(15.2, 9.3, 7.6, 11.9, 10.4, 9.7, 20.4, 9.4, 11.5, 9.4, 8.3)
    )
fivenum(c(15.2, 9.3, 7.6, 11.9, 10.4, 9.7, 20.4, 9.4, 11.5, 9.4, 8.3))
```

    ## [1]  7.60  9.35  9.70 11.70 20.40

``` r
mean(c(15.2, 9.3, 7.6, 11.9, 10.4, 9.7, 20.4, 9.4, 11.5, 9.4, 8.3))
```

    ## [1] 11.19091

``` r
var(problem1_df$fe_level)
```

    ## [1] 13.55691

``` r
sd(problem1_df$fe_level)
```

    ## [1] 3.681971

# Problem 2

# Problem 3

## Importing Data

``` r
problem3_df = read_table("./data/Pacemaker.txt")
```

    ## Parsed with column specification:
    ## cols(
    ##   Time = col_double()
    ## )

\#\#Create a histogram

``` r
hist(problem3_df$Time, col = "lightblue", main = "Pacemaker Data", xlab = "Time in Months")
```

![](template_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

## Calculate the mean, median, variance and standard deviation.

``` r
mean(problem3_df$Time)
```

    ## [1] 18.94382

``` r
median(problem3_df$Time)
```

    ## [1] 20

``` r
var(problem3_df$Time)
```

    ## [1] 49.64454

``` r
sd(problem3_df$Time)
```

    ## [1] 7.045888

## Calculate range

``` r
range(problem3_df$Time)
```

    ## [1]  2 34

# Problem 4

## Read in data and Create a boxplot

``` r
problem4_df = read_table2("./data/BloodPressure.txt")
```

    ## Warning: Missing column names filled in: 'X3' [3]

    ## Parsed with column specification:
    ## cols(
    ##   Race = col_character(),
    ##   BP = col_double(),
    ##   X3 = col_character()
    ## )

    ## Warning: 40 parsing failures.
    ## row col  expected    actual                       file
    ##   1  -- 3 columns 2 columns './data/BloodPressure.txt'
    ##   2  -- 3 columns 2 columns './data/BloodPressure.txt'
    ##   3  -- 3 columns 2 columns './data/BloodPressure.txt'
    ##   4  -- 3 columns 2 columns './data/BloodPressure.txt'
    ##   5  -- 3 columns 2 columns './data/BloodPressure.txt'
    ## ... ... ......... ......... ..........................
    ## See problems(...) for more details.

``` r
ggplot(problem4_df, aes(x= Race, y= BP, fill = Race)) + 
  geom_boxplot(fill="lightblue")+
  labs(title="Blood Lead Levels", x="Race", y = "Blood Lead Level (micrograms per deciliter)")+
  theme_classic()
```

![](template_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

# Problem 5

Create a random distribution of 20 test scores with mean = 250, sd = 50.

``` r
set.seed(124)
problem5_df = 
  tibble(
    student = 1:20,
    testscore = rnorm(20, 250, 50)
  )
mean1 = mean(problem5_df$testscore)
mean1
```

    ## [1] 250.5601

``` r
var1 = var(problem5_df$testscore)
var1
```

    ## [1] 2049.479

Now increase the test scores by 25% and calculate the new variance.

``` r
problem5_df_2 = problem5_df$testscore*1.25
mean2 = mean(problem5_df_2)
mean2
```

    ## [1] 313.2002

``` r
var2 = var(problem5_df_2)
var2
```

    ## [1] 3202.311

Calculations, ?change in mean and variance.

``` r
change_in_mean = mean2 / mean1
change_in_mean
```

    ## [1] 1.25

``` r
change_in_var = var2 / var1
change_in_var
```

    ## [1] 1.5625

# Problem 7

``` r
problem7_df = c(60, 30, 5, 1, 78, 16, 3, 2, 86, 10, 2, 1)
p7_total = sum(problem7_df)
(78+16+3+2) / p7_total *100
```

    ## [1] 33.67347

``` r
(60 + 78 + 86) / 294
```

    ## [1] 0.7619048

``` r
(60+ 30+ 5+ 1) / 294
```

    ## [1] 0.3265306
