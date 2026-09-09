# Format date columns in POWER data frame for the ag community

Formats columns as integers for DOY and adds columns for year, month and
day.

## Usage

``` r
.format_dates_ag(power_response)
```

## Arguments

- power_response:

  A tidy data.frame resulting from
  [.build_query](https://docs.ropensci.org/nasapower/reference/dot-build_query.md).

## Value

A tidy data frame of 'POWER' data with additional date information
columns.
