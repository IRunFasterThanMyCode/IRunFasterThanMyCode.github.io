How To Use R
============

This tutorial is a basic introduction to R. R is a software package that is a free to use open-source version of the S programming language. It is designed mainly for running statistical analyses and is very powerful in this regard. Follow through the tutorial and run the example commands by typing them into the command line as you go to see what happens. Don’t be afraid to play around with things as you go -- it’s the best way to find out what certain functions do.

You will notice that I have added comments to some of the code using the <tt>\#</tt> comment character. Everything to the right of this character is ignored by R. This can be used to add comments to your code, for instance to explain what a particular code chunk does. You can NEVER have too many comments!

1: Installing R
---------------

First of all, you will need to download and install R. The R website can be found at [r-project.org](http://www.r-project.org). R is updated quite regularly -- there is an updated release roughly every 6 months, with various developmental versions released between the official versions. The functions in R are actively maintained to ensure that they run as they should, and new functionality is added all of the time.

The current version is 3.3.2. To download it, go to the Comprehensive R Archive Network ([cran.r-project.org](https://cran.r-project.org)). There are ready-made binaries available for MAC, windows, and most Linux distributions, so follow the links and download as instructed. You can also download the source code in a tarball, and can compile and install it using <tt>make</tt>.

It is also worth taking a look at the Integrated Development Environment [RStudio](https://www.rstudio.com), which is a great open-source interface for R.

2: Basics of R
--------------

### 2.1: Introduction

Open the R environment. This is a command line version allowing you to see the results of the commands that you enter as you run them.

The command line is shown by the <tt>&gt;</tt> character. Simply type your command here and press return to see the results. If your command is not complete, then the command line character will change to a <tt>+</tt> to indicate that more input is required, for instance a missing parenthesis:

``` r
print ("Hello World!" # Final parenthesis missing - CTRL+c or ESC to end
```

R stores "variables" using names made up of characters and numbers. A variable, as the name suggests, is a data "object" that can take any value that you want, and can be changed.

The variable name can be anything that you like, although it must begin with a character. Whilst it is perfectly acceptable to use simple variable names such as <tt>x</tt>, <tt>y</tt>, <tt>i</tt>, I recommend using a more descriptive name (e.g. <tt>patient\_height</tt> instead of <tt>x</tt>). There are lots of different variable naming conventions to choose from (e.g. see [here](https://en.wikipedia.org/wiki/Naming_convention_(programming))), but once you have chosen one try and stick to it.

To assign a value to the variable, use the &lt;tt&gt;&lt;-</tt> command (less-than symbol followed by minus symbol). You can also use the <tt>=</tt> symbol, but this has other uses (for instance using <tt>==</tt> to test for equality) so I prefer to use the &lt;tt&gt;&lt;-</tt> command:

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

Simple arithmetic can be performed using the standard arithmetic operators (<tt>+</tt>, <tt>-</tt>, <tt>\*</tt>, <tt>/</tt>), as well as the exponent operator (<tt>^</tt>). There is a level of precedence to these functions -- the exponent will be calculated first, followed by multiplication and division, followed by plus and minus. For this reason, you must be careful that your arithmetic is doing what you expect it to do. You can get around this by encapsulating subsets of the sum in parentheses, which will be calculated from the inside out:

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

Another operator that you may not have seen before is the "modulo" operator (<tt>%%</tt>), which gives you the remainder left after dividing by the number:

``` r
6%%2 # 6 is divisible by 2 exactly three times, so the remainder is 0 
```

    ## [1] 0

``` r
6%%4 # 6 is divisible by 4 one time with a remainder of 2
```

    ## [1] 2

You can also use other variables in these assignments:

``` r
x <- 1
y <- x
y
```

    ## [1] 1

``` r
z <- x + y 
z
```

    ## [1] 2

### 2.2 Data Classes

Variables can take many forms, or "classes". The most common are "numeric" (which you can do numerical calculations on), character (can contain letters, numbers, symbols etc., but cannot run numerical calculations), and logical (TRUE or FALSE). The speech marks character <tt>"</tt> is used to show that the class of y is "character". You can also use the apostrophe <tt>'</tt>. There *is* a difference between these, but for now this is not important. You can check the class of a variable by using the <tt>class()</tt> function:

``` r
x <- 12345
class(x)
```

    ## [1] "numeric"

``` r
y <- "12345"
class(y)
```

    ## [1] "character"

Addition is a well-defined operation on numerical objects, but is not defined on character class objects. Attempting to use a function which has not been defined for the object in question will throw an error:

``` r
x + 1 # x is numeric, so addition is well defined
```

    ## [1] 12346

``` r
y + 1 # y is a character, so addition is not defined - produces an error
```

    ## Error in y + 1: non-numeric argument to binary operator

To see which objects are currently present in the R environment, use the <tt>ls()</tt> command. To remove a particular object, use the <tt>rm()</tt> command. *BE CAREFUL* -- once you have removed an object, it is gone forever!

``` r
x <- 5
ls ()
```

    ## [1] "x" "y" "z"

``` r
rm(x)
ls ()
```

    ## [1] "y" "z"

``` r
rm(list=ls()) # Removes all objects in the current R session
ls ()
```

    ## character(0)

You can also change the class of a variable by assigning to the <tt>class()</tt> function:

``` r
x <- "12345"
x+1
```

    ## Error in x + 1: non-numeric argument to binary operator

``` r
class(x)
```

    ## [1] "character"

``` r
class(x) <- "numeric" 
class(x)
```

    ## [1] "numeric"

``` r
x+1
```

    ## [1] 12346

The other important data class is "logical", which is simply a binary TRUE or FALSE value. There are certain operators that are used to compare two variables. The obvious ones are "is less than" (&lt;tt&gt;&lt;</tt>), "is greater than" (<tt>&gt;</tt>), "is equal to"" (<tt>==</tt>). You can also combine these to see "is less than or equal to" (&lt;tt&gt;&lt;=</tt>) or "is greater than or equal to" (<tt>&gt;=</tt>). If the statement is true, then it will return the output "TRUE". Otherwise it will return "FALSE":

``` r
x <- 2
y <- 3
x <= y
```

    ## [1] TRUE

``` r
x >= y
```

    ## [1] FALSE

You can also combine these logical tests to ask complex questions by using the "AND" (<tt>&&</tt>) or the "OR" (<tt>||</tt>) operators. You can also negate the output of a logical test by using the "NOT" (<tt>!</tt>) operator. This lets you test for very specific events in your data. Again, I recommend using parentheses to break up your tests to ensure that the tests occur in the order which you expect:

``` r
x <- 3
y <- 7
z <- 6
(x <= 3 && y >= 8) && z == 6  
```

    ## [1] FALSE

``` r
(x <= 3 && y >= 8) || z == 6 
```

    ## [1] TRUE

One important set of functions are the log and exponential functions. The exponential function is the function \(e^x\), such that \(e^x\) is its own derivate (\(\frac{d}{dx} e^x) = e^x\)). The value e is the constant 2.718281828..., which is the limit \(\lim_{n \to \infty} (1+\frac{1}{n})^n\). It is a very important value in mathematics (hence why it has its own constant). Logarithms are the inverse of exponents, with natural log being log base \(e\). Here are some examples:
