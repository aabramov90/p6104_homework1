Homework 1
================
Alexey Abramov

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

Problem 1

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

Problem 3

Importing Data

``` r
problem3_df = read_table("./Pacemaker.txt")
```

    ## Parsed with column specification:
    ## cols(
    ##   Time = col_double()
    ## )

Create a histogram

``` r
hist(problem3_df$Time, col = "lightblue", main = "Pacemaker Data", xlab = "Time in Months")
```

![](template_files/figure-gfm/unnamed-chunk-4-1.png)<!-- -->

Calculate the mean, median, variance and standard deviation.

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
