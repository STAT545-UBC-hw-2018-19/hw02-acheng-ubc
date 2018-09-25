STAT545 Assignment 2
================
Alex
September 24, 2018

Initializing Gapminder Dataset and Libraries
--------------------------------------------

``` r
library(tidyverse)
```

    ## -- Attaching packages ---------------------------------- tidyverse 1.2.1 --

    ## v ggplot2 3.0.0     v purrr   0.2.5
    ## v tibble  1.4.2     v dplyr   0.7.6
    ## v tidyr   0.8.1     v stringr 1.2.0
    ## v readr   1.1.1     v forcats 0.2.0

    ## -- Conflicts ------------------------------------- tidyverse_conflicts() --
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

``` r
library(ggplot2)
library(gapminder)
```

"Smell test" the data
---------------------

``` r
typeof(gapminder)
```

    ## [1] "list"

The gapminder object is a list.

``` r
class(gapminder)
```

    ## [1] "tbl_df"     "tbl"        "data.frame"

It's class is a tibble, which is a type of data frame.

``` r
dim(gapminder)
```

    ## [1] 1704    6

Using the`dims()` function we get that there are 1706 rows (observations) for 6 columns (variables). We could also get size information using the `ncol()` or `nrow()` functions

``` r
summary(gapminder)
```

    ##         country        continent        year         lifeExp     
    ##  Afghanistan:  12   Africa  :624   Min.   :1952   Min.   :23.60  
    ##  Albania    :  12   Americas:300   1st Qu.:1966   1st Qu.:48.20  
    ##  Algeria    :  12   Asia    :396   Median :1980   Median :60.71  
    ##  Angola     :  12   Europe  :360   Mean   :1980   Mean   :59.47  
    ##  Argentina  :  12   Oceania : 24   3rd Qu.:1993   3rd Qu.:70.85  
    ##  Australia  :  12                  Max.   :2007   Max.   :82.60  
    ##  (Other)    :1632                                                
    ##       pop              gdpPercap       
    ##  Min.   :6.001e+04   Min.   :   241.2  
    ##  1st Qu.:2.794e+06   1st Qu.:  1202.1  
    ##  Median :7.024e+06   Median :  3531.8  
    ##  Mean   :2.960e+07   Mean   :  7215.3  
    ##  3rd Qu.:1.959e+07   3rd Qu.:  9325.5  
    ##  Max.   :1.319e+09   Max.   :113523.1  
    ## 

``` r
class(gapminder$country)
```

    ## [1] "factor"

``` r
class(gapminder$continent)
```

    ## [1] "factor"

``` r
class(gapminder$year)
```

    ## [1] "integer"

``` r
class(gapminder$lifeExp)
```

    ## [1] "numeric"

``` r
class(gapminder$pop)
```

    ## [1] "integer"

``` r
class(gapminder$gdpPercap)
```

    ## [1] "numeric"

Using `summary()` we can get a quick overview of the variables in *gapminder* and surmise the data type of each variable, but we can also make sure by calling the `class()` function.

From this we get the following data types in *gapminder*:

| Variable  | Data Type |
|-----------|-----------|
| country   | factor    |
| continent | factor    |
| year      | integer   |
| lifeExp   | numeric   |
| pop       | integer   |
| gdpPercap | numeric   |
