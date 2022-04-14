This has some tips and tricks for getting the EIA data for the class project

# Downloading data
There are several methods.  All but the first method require you to get an **API key** https://www.eia.gov/opendata/register.cfm
1. Direct download from web browser.
    - This is easy to get started with, but slow and clunky. Navigate the EIA website to https://www.eia.gov/opendata/qb.php?category=3389994 (PSCO demand data), which has two child series
    - The child series are "Demand for Public Service Company of Colorado (PSCO), hourly - UTC time" and a similar version (but local time). Either one works, as long as we account for the time offset later
    - Click on either child series and wait for the page to load (may be 10 min or so). It loads all the data onto the page and also gives you a download csv button
    (Note: the link is `https://www.eia.gov/opendata/qb.php?category=3389994&sdid=EBA.PSCO-ALL.D.H` for that first series; from this link, we note that the "Series ID" is `EBA.PSCO-ALL.D.H` (and `EBA.PSCO-ALL.D.HL` for the local time version)
    - Download the csv and you're done
2. Use the `EIA` R package at https://cran.r-project.org/web/packages/eia/
    - This seems to be *very nice* and fully featured, at the expense of a learning curve.  
    - e.g., it provides utilities to convert dates, it provides tools to update a dataset whenever new data is available, you can download a given time range of data, etc.
    - I haven't tried it myself, but if you haven't made another method work, I'd start with this. 
    - It seems to have good documentation, including a [reference manual](https://cran.r-project.org/web/packages/eia/eia.pdf) and "vignettes" like [package overview](https://cran.r-project.org/web/packages/eia/vignettes/eia.html) and [EIA time series data](https://cran.r-project.org/web/packages/eia/vignettes/series.html)
3. Use the `EIAdata` R package at https://cran.r-project.org/web/packages/EIAdata/
    - This is a simpler but still useful R package. I was able to get it working quite quickly using their [reference manual](https://cran.r-project.org/web/packages/EIAdata/EIAdata.pdf)
    ```R
    install.packages("EIAdata") # may also install dependencies ‘XML’, ‘xts’, ‘zoo’
    library(EIAdata)
    key <- "YOUR-API-KEY"
    # getCatEIA(key=key) # all view categories
    # getCatEIA(key=key, cat=2123635) # U.S. Electric System Operating Data
    # getCatEIA(key=key, cat=2122628) # Demand
    # getCatEIA(key=key, cat=3389994) # Public Service Company of Colorado (PSCO)
    data <- getEIA(ID = "EBA.PSCO-ALL.D.HL", key = key) # this is the data we want
    ```
4. Direct download
    - Barebone instructions are here: https://www.eia.gov/opendata/commands.php
    - An advantage of this method is that you can download just a subset of the data, e.g., `num=40` gives you just the most recent 40 data points, or use `start=...` and `end=...`
    - The key is getting the right URL.  It should look something like this:

    ```
    https://api.eia.gov/series/?series_id=EBA.PSCO-ALL.D.HL&api_key=YOUR-API-KEY&out=xml&num=40
    ```
    where you can adjust the output format (`xml` or `json`), optionally specify the number (e.g., `num=40`) for faster downloading, etc. Change `EBA.PSCO-ALL.D.HL` to `EBA.PSCO-ALL.D.H` if you want UTC. 
    Adjust `YOUR-API-KEY` to be whatever your API key is.

    - Next, you must download from this URL.  
    - In unix / linux / MacOS, from a command line, use `curl` (note: `wget` does *not* work!) like
     
    ```
    curl -v 'https://api.eia.gov/series/?series_id=EBA.PSCO-ALL.D.HL&api_key=YOUR-API-KEY&out=xml' -o'data.xml'
    ```
    which saves it to a file called `data.xml`.

    - or in `R`, load (and install if needed) the `httr` package, then run
    ```
    doc <- httr::GET("https://api.eia.gov/series/?series_id=EBA.PSCO-ALL.D.HL&api_key=YOUR-API-KEY&out=xml"
    ```
    and it will load it directly into R (though it's xml or json, so you'll need to parse it; R has libraries to help with this).

# Parsing data
## Dates
If you're given a date string from a data file like `04/06/22 12:00 -0600`, R probably reads this as a string, and now we want to make it something numeric and more useful. You can use the `as.POSIXct` function to parse the date string and return something of a nicer format.  e.g.,
```R
timeString <- '04/06/22 12:00 -0600'
time       <- as.POSIXct( timeString, tz="", "%m/%d/%y %R %z" )
```
The 3rd argument to `as.POSIXct` tells it how to parse the string, with `%m` standing for month, `%y` stands for a two-digit year like 22 (and `%Y` is a 4-digit year like 2022), etc.  Full documentation on the parsing is available at the help file for [strptime](https://www.rdocumentation.org/packages/base/versions/3.6.2/topics/strptime).
You can also use `as.Date` except this only works with dates and you lose the hourly data.

The package `lubridate` has some good utilities for working with dates.
