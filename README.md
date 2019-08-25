[![Travis-CI Build Status](https://travis-ci.org/dashaub/lintr.svg?branch=master)](https://travis-ci.org/dashaub/lintr)
[![CircleCI](https://circleci.com/gh/dashaub/lintr.svg?style=svg)](https://circleci.com/gh/dashaub/lintr)

# lintr
A command tool wrapping the R package "lintr" for static R code analysis


# Why?
The ["linter"](https://github.com/jimhester/lintr#available-linters) package from Jim Hester is an excellent R package that lints R code and has integrations with RStudio, Emacs, Vim, Sublime, and Atom. This project is a very simple wrapper around this so that you can use the tool from the command line.

# Installation

## Debian/Ubuntu
In the future, this tool is planned to be in the Debian/Ubuntu repos. On the (as of yet unreleased) Debian Bullseye and Ubuntu 20.04, the package will be easily installed with
```
$ sudo apt install lintr
```

## Manual

The command line tool requires `r` and the "lintr" CRAN package. Install R according to the directions provided on the [R-project](https://www.r-project.org/). The "lintr" R package can then be installed from CRAN using
```
$ Rscript -e 'install.packages("lintr")'
```

Now install the `lintr` script
```
$ sudo curl https://raw.github.com/dashaub/lintr/master/lintr -Lo /opt/lintr
```

# Usage

We can lint the provided `example.R` file.
```
$ lintr example.R 
example.R:2:3: style: Use <-, not =, for assignment.
a = 3
  ^
example.R:3:7: style: Put spaces around all infix operators.
a <- a*2
     ~^~
example.R:6:12: style: Only use double-quotes.
message <- 'hello world'
           ^~~~~~~~~~~~~
example.R:7:1: style: Variable and function names should be all lowercase.
myFunc <- function()
^~~~~~
example.R:8:1: style: Opening curly braces should never go on their own line and should always be followed by a new line.
{
^
example.R:9:12: warning: no visible binding for global variable ‘missing_var’
    return(missing_var)
           ^~~~~~~~~~~
example.R:12:1: style: Variable and function names should be all lowercase.
myFunc()
^~~~~~
example.R:13:1: style: Trailing blank lines are superfluous.

^
```
