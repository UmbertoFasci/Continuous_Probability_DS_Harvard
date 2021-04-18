Continuous\_Probability
================
Umberto Fasci

## Continuous Probability

Here, the vector x is characterized as male heights in the height
dataset:

``` r
library(tidyverse)
```

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.0 ──

    ## ✓ ggplot2 3.3.3     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.0     ✓ dplyr   1.0.5
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   1.4.0     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(dslabs)
data(heights)
x <- heights %>% filter(sex == "Male") %>% .$height
```

Defining the empirical distribution function:

``` r
F <- function(a) mean(x<=a)
```

## eCDF approach

If one of the male students in this dataset is chosen, what is the
chance that he is taller than 70.5 inches?

Using eCDF we can simply answer this:

``` r
1 - F(70.5)
```

    ## [1] 0.3633005

Using this cumulative probability function we can compute the
probability of any subset within the data.

## Example

What is the probability of a student being between 65 and 70 in?:

``` r
F(70) - F(65)
```

    ## [1] 0.5172414

## Notes

The cumulative distribution function (CDF) is a distribution function
for continuous data (x) that reports the proportion of the data below
*a* for all values of *a*:

*F*(*a*) = *P**r*(*x* ≤ *a*)

The CDF is the probability distribution function for continuous
variables. For example, to determine the probability that a male student
is taller than 70.5 inches given a vector of male heights *x*, we can
use the CDF:
