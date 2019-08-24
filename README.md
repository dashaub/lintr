# lintr
A command tool wrapping the R package "lintr" for static R code analysis

# Why?
The ["linter"](https://github.com/jimhester/lintr#available-linters) package from Jim Hester is an excellent R package that lints R code and has integrations with RStudio, Emacs, Vim, Sublime, and Atom. This project is a very simple wrapper around this so that you can use the tool from the command line.

# Installation

## Debian/Ubuntu
On the (as of yet unreleased) Debian Bullseye and Ubuntu 20.04, the package can be easily installed with
```
$ sudo apt install lintr
```

## Manual

The command line tool requires `r` and the "lintr" package. Install R according to the directions provided on the [R-project](https://www.r-project.org/). The "lintr" R package can then be installed from CRAN using
```
$ Rscript -e 'install.packages("lintr")'
```

Now install the `lintr` script
```
$ sudo curl https://raw.github.com/ellisp/forecastHybrid/master/build.R -Lo /opt/lintr
```

# Usage

We can lint the provided `example.R` file.
```
$ lintr example.R
example.R:3:2: style: Put spaces around all infix operators.
a*2
~^~
example.R:5:1: style: Opening curly braces should never go on their own line and should always be followed by a new line.
{
^
example.R:6:12: warning: no visible binding for global variable ‘a’, Did you mean 'ar'?
    return(a)
           ^
example.R:8:1: style: Trailing blank lines are superfluous.

^

```
