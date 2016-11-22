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

Table of Contents
-----------------

1.  [Installing R](#1installR)

1: Installing R<a name="installR" />
------------------------------------

First of all, you will need to download and install R. The R website can be found at [r-project.org](http://www.r-project.org). R is updated quite regularly -- there is an updated release roughly every 6 months, with various developmental versions released between the official versions. The functions in R are actively maintained to ensure that they run as they should, and new functionality is added all of the time.

The current version is 3.3.2. To download it, go to the Comprehensive R Archive Network ([cran.r-project.org](https://cran.r-project.org)). There are ready-made binaries available for MAC, windows, and most Linux distributions, so follow the links and download as instructed. You can also download the source code in a tarball, and can compile and install it using `make`.

It is also worth taking a look at the Integrated Development Environment [RStudio](https://www.rstudio.com), which is a great open-source interface for R.
