# R Resources

This page contains information on the R programming language

There are lots of great tutorials on the internet, so we don't want to duplicate things. Rather, we can use this page to list our favorite resources.


### How to use this page

This document is starting off small, with just a few items added by the instructor. But because this is on github, students can contribute their own ideas using a pull (merge) request, and then the admins for this github repo (the instructor and TA) can accept the merge (or modify or reject it).

Find a great R tutorial on Youtube? Please add the link to this website!

You can edit this document using the github website itself -- look for the pencil icon.

This document is written in [markdown](https://en.wikipedia.org/wiki/Markdown), which is a very simple way to include links and things like that. It takes about 2 minutes to learn the most important basics (in fact, you probably don't need to "learn" it, just follow the examples).

## Resources

#### General category

- When you search google for "R [something]", it's hard for google to know if you mean the letter "R" or the language "R" (though it probably does a fairly good job).  An alternative is to use [rseek](https://rseek.org/), a dedicated search engine for R that is powered by google.
- [An Introduction to R](https://cran.r-project.org/doc/manuals/R-intro.pdf) is an official guide to R written by the R developers.
- [R tutorial](Code/R_tutorial.ipynb) was developed by Prof. Will Kleiber when he taught this course in 2018. It's a very brief introduction to R, and I've adapted it to work with Colab
- Most of our demonstrations will be using [github](http://github.com) in conjunction with [R via colab](https://colab.research.google.com/#create=true&language=r) (you can use the alias [`https://colab.to/r`](https://colab.to/r)).
- For more involved coding projects, we recommend use of an [IDE](https://en.wikipedia.org/wiki/Integrated_development_environment) that supports R. The standard choice is [R Studio](https://www.rstudio.com/) which is excellent, but you can also use multi-purpose IDEs like [VS Code](https://code.visualstudio.com/).  When installing these IDEs, you still need to [install R itself](https://cran.r-project.org/bin).


#### R and Jupyter/Colab
- To make a new R document in Colab, go to [https://colab.to/r](https://colab.research.google.com/#create=true&language=r)
- From colab, you can manually upload/download files, or even mount google drive (google this to find out how, e.g., https://towardsdatascience.com/how-to-use-r-in-google-colab-b6e02d736497)
- You can use R within a *python* Colab file, but for this class I wouldn't recommend it

#### Packages
- [Rstudio's suggested list of top packages](https://support.rstudio.com/hc/en-us/articles/201057987-Quick-list-of-useful-R-packages) including [ggplot2](http://docs.ggplot2.org/current/) for nice plotting, [tidyverse](https://www.tidyverse.org/) packages like `dyplyr`, `tidyr`, `stringr` and `lubridate`
  - For time series, there is [zoo](https://cran.rstudio.com/web/packages/zoo) ( the most popular format for saving time series objects in R), [xts](https://cran.rstudio.com/web/packages/xts) (flexible tools for manipulating time series data sets) and [quantmod](http://www.quantmod.com/) (for downloading financial data, plotting common charts, and doing technical analysis).

#### Cheatsheets
- [RStudio cheat sheet collection](https://github.com/rstudio/cheatsheets) is quite good
  - [base R](https://github.com/rstudio/cheatsheets/blob/main/base-r.pdf)
  - [Time series cheat sheet](https://github.com/rstudio/cheatsheets/blob/main/time-series.pdf) 
  - [Data visualization with `ggplot2`](https://github.com/rstudio/cheatsheets/blob/main/data-visualization.pdf)

#### R and time series
- A [curated list of time series topics in R](https://cran.r-project.org/web/views/TimeSeries.html).
- The [Time Series Analysis and Its Applications With R Examples — 4th Edition](https://www.stat.pitt.edu/stoffer/tsa4/) by Shumway & Stoffer has some tutorials
  - [R Time Series Quick Fix](https://www.stat.pitt.edu/stoffer/tsa4/R_toot.htm)
  - [R Time Series Graphics Fix](https://www.stat.pitt.edu/stoffer/tsa4/tsgraphics.htm)
- [Time Series and Forecasting, by Quick-R](https://www.statmethods.net/advstats/timeseries.html) has some basic info too

