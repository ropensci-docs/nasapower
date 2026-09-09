# {nasapower}: NASA POWER API Client

## POWER data vs {nasapower}

Please note that {nasapower} is **NOT** the source of NASA POWER data.
It is only an API client that allows easy access to the data.
{nasapower} does not redistribute the data or provide it in any way, *we
encourage users to follow the requests of the POWER Project Team and
properly acknowledge them for the data rather than citing this package*
(unless you have actually used it in your work).

> *When POWER data products are used in a publication, we request the
> following acknowledgement be included: “The data was obtained from the
> National Aeronautics and Space Administration (NASA) Langley Research
> Center (LaRC) Prediction of Worldwide Energy Resource (POWER) Project
> funded through the NASA Earth Science/Applied Science Program.”*

The previous statement that properly cites the POWER data is different
than the citation for {nasapower}. To cite this R package, {nasapower},
please use the output from `citation(package = "nasapower")`.

## About {nasapower}

{nasapower} aims to make it quick and easy to automate *downloading* of
the [NASA-POWER](https://power.larc.nasa.gov) global meteorology,
surface solar energy and climatology data in your R session as a tidy
data frame `tibble` object for analysis and use in modelling or other
purposes. POWER (Prediction Of Worldwide Energy Resource) data are
freely available for download with varying spatial resolutions dependent
on the original data and with several temporal resolutions depending on
the POWER parameter and community.

**Note that the data are not static and may be replaced with improved
data.** Please see <https://power.larc.nasa.gov/docs/services/> for
detailed information in this regard.

### Quick start

{nasapower} can easily be installed using the following code.

#### From CRAN

The stable version is available through CRAN.

``` r

install.packages("nasapower")
```

#### From R-Universe

A development version is available through R-Universe if you prefer.

``` r

install.packages("nasapower", repos = "https://ropensci.r-universe.dev")
```

### Example

Fetch daily “ag” community temperature, relative humidity and
precipitation for January 1, 1985 for Kingsthorpe, Queensland,
Australia.

``` r

library("nasapower")
daily_ag <- get_power(
  community = "ag",
  lonlat = c(151.81, -27.48),
  pars = c("RH2M", "T2M", "PRECTOTCORR"),
  dates = "1985-01-01",
  temporal_api = "daily"
)
daily_ag
```

    ## ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

    ## 

    ## ── NASA/POWER Source Native Resolution Daily Data  ──────────────────────────────────────────────────────────────────────────────────────────────────────────

    ## Dates (month/day/year): 01/01/1985 through 01/01/1985 in LST

    ## Location: latitude -27.48 longitude 151.81

    ## elevation from MERRA-2: Average for 0.5 x 0.625 degree lat/lon region = 442.77 meters

    ## The value for missing source data that cannot be computed or is outside of the sources availability range: NA

    ## parameter(s):

    ## ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────

    ## Parameters:

    ## RH2M MERRA-2 Relative Humidity at 2 Meters (%) ; T2M MERRA-2 Temperature at 2 Meters (C) ; PRECTOTCORR MERRA-2 Precipitation Corrected (mm/day)

    ## ─────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────
    ## # Tibble (class tbl_df) 10 x 1:
    ##  │LON  │LAT  │YEAR │MM   │DD   │DOY  │YYYYMMDD  │RH2M │T2M  │PRECTOTCORR
    ##  │<dbl>│<dbl>│<dbl>│<int>│<int>│<int>│<oth>     │<dbl>│<dbl>│<dbl>
    ## 1│  152│  -27│ 1985│    1│    1│    1│1985-01-01│   55│   25│        0.9

## Documentation

More documentation is available in the vignette in your R session,
[`vignette("nasapower")`](https://docs.ropensci.org/nasapower/articles/nasapower.md)
or available online,
<https://docs.ropensci.org/nasapower/articles/nasapower.html>.

## Meta

- Please note that this package is released with a [Contributor Code of
  Conduct](https://ropensci.org/code-of-conduct/). By contributing to
  this project, you agree to abide by its terms.

- Please [report any issues or
  bugs](https://github.com/ropensci/nasapower/issues).

- License: MIT

### Citing {nasapower}

When citing the use of this package, please use the output from,

``` r

library("nasapower")
citation("nasapower")
```

    ## To cite package 'nasapower' in publications use:
    ##
    ##   Sparks A (2018). "nasapower: A NASA POWER Global Meteorology, Surface Solar Energy and Climatology Data Client for R." _The Journal of
    ##   Open Source Software_, *3*(30), 1035. doi:10.21105/joss.01035 <https://doi.org/10.21105/joss.01035>.
    ##
    ## A BibTeX entry for LaTeX users is
    ##
    ##   @Article{,
    ##     author = {Adam H. Sparks},
    ##     title = {nasapower: A NASA POWER Global Meteorology, Surface Solar Energy and Climatology Data Client for R},
    ##     doi = {10.21105/joss.01035},
    ##     year = {2018},
    ##     month = {oct},
    ##     publisher = {The Open Journal},
    ##     volume = {3},
    ##     number = {30},
    ##     pages = {1035},
    ##     journal = {The Journal of Open Source Software},
    ##   }

## References

<https://power.larc.nasa.gov>

<https://power.larc.nasa.gov/docs/methodology/>

## Contributors

All contributions to this project are gratefully acknowledged using the
[`allcontributors` package](https://github.com/ropensci/allcontributors)
following the [all-contributors](https://allcontributors.org)
specification. Contributions of any kind are welcome!

### Code

[TABLE]

### Issue Authors

[TABLE]

### Issue Contributors

[TABLE]
