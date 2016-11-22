---
layout: page
comments: true
title: "R Tutorial"
tags: R, tutorial 
permalink: /RTutorial/
output:
  md_document:
    variant: markdown_github
    preserve_yaml: true
---

How To Use R
============

This tutorial is a basic introduction to R that was originally written for biologists to get a basic understanding of how R functions. R is a software package that is a free to use open-source version of the S programming language. It is designed mainly for running statistical analyses and is very powerful in this regard. Follow through the tutorial and run the example commands by typing them into the command line as you go to see what happens. Don’t be afraid to play around with things as you go -- it’s the best way to find out what certain functions do.

You will notice that I have added comments to some of the code using the `#` comment character. Everything to the right of this character is ignored by R. This can be used to add comments to your code, for instance to explain what a particular code chunk does. You can NEVER have too many comments!

1: Installing R
---------------

First of all, you will need to download and install R. The R website can be found at [r-project.org](http://www.r-project.org). R is updated quite regularly -- there is an updated release roughly every 6 months, with various developmental versions released between the official versions. The functions in R are actively maintained to ensure that they run as they should, and new functionality is added all of the time.

The current version is 3.3.2. To download it, go to the Comprehensive R Archive Network ([cran.r-project.org](https://cran.r-project.org)). There are ready-made binaries available for MAC, windows, and most Linux distributions, so follow the links and download as instructed. You can also download the source code in a tarball, and can compile and install it using `make`.

It is also worth taking a look at the Integrated Development Environment [RStudio](https://www.rstudio.com), which is a great open-source interface for R.

2: Basics of R
--------------

### 2.1: Introduction

Open the R environment. This is a command line version allowing you to see the results of the commands that you enter as you run them.

The command line is shown by the `>` character. Simply type your command here and press return to see the results. If your command is not complete, then the command line character will change to a `+` to indicate that more input is required, for instance a missing parenthesis:

``` r
print ("Hello World!"
```

    ## Error: <text>:2:0: unexpected end of input
    ## 1: print ("Hello World!"
    ##    ^

R stores "variables" using names made up of characters and numbers. A variable, as the name suggests, is a data "object" that can take any value that you want, and can be changed.

The variable name can be anything that you like, although it must begin with a character. Whilst it is perfectly acceptable to use simple variable names such as `x`, `y`, `i`, I recommend using a more descriptive name (e.g. `patient_height` instead of `x`). There are lots of different variable naming conventions to choose from (e.g. see [here](https://en.wikipedia.org/wiki/Naming_convention_(programming))), but once you have chosen one try and stick to it.

To assign a value to the variable, use the `<-` command (less-than symbol followed by minus symbol). You can also use the `=` symbol, but this has other uses (for instance using `==` to test for equality) so I prefer to use the `<-` command:

``` r
x <- 3
x # Returns the value stored in 'x' - currently 3
```

    ## [1] 3

``` r
x <- 5
x # Returns the value stored in 'x' - now 5
```

    ## [1] 5

Simple arithmetic can be performed using the standard arithmetic operators (`+`, `-`, `*`, `/`), as well as the exponent operator (`^`). There is a level of precedence to these functions -- the exponent will be calculated first, followed by multiplication and division, followed by plus and minus. For this reason, you must be careful that your arithmetic is doing what you expect it to do. You can get around this by encapsulating subsets of the sum in parentheses, which will be calculated from the inside out:

``` r
1+2*3 
```

    ## [1] 7

``` r
(1 + 2) * 3 
```

    ## [1] 9

``` r
1 + (2 * 3) 
```

    ## [1] 7

Personally I think that you can NEVER have too many parentheses -- they ensure that your equations are doing what they should, and they can help improve the readability of things making it easier to see what a calculation is trying to achieve.

Another operator that you may not have seen before is the "modulo" operator (`%%`), which gives you the remainder left after dividing by the number:

``` r
6%%2 # 6 is divisible by 2 exactly three times
```

    ## [1] 0

``` r
6%%4 # 6 is divisible by 4 one time with a remainder of 2
```

    ## [1] 2
