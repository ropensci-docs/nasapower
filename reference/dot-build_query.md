# Construct a list of options to pass to the POWER API

Construct a list of options to pass to the POWER API

## Usage

``` r
.build_query(
  community,
  lonlat_identifier,
  pars,
  dates,
  site_elevation,
  wind_elevation,
  wind_surface,
  time_standard
)
```

## Arguments

- community:

  A validated value for `community`.

- lonlat_identifier:

  A list of values, a result of
  [.check_lonlat](https://docs.ropensci.org/nasapower/reference/dot-check_lonlat.md).

- pars:

  A validated value from
  [.check_pars](https://docs.ropensci.org/nasapower/reference/dot-check_pars.md).

- dates:

  A list of values, a result of
  [.check_dates](https://docs.ropensci.org/nasapower/reference/dot-check_dates.md).

- site_elevation:

  A validated value passed by `check_inputs`.

- wind_elevation:

  A validated value passed by `check_inputs`.

- wind_surface:

  A validated value passed by `check_inputs`.

- time_standard:

  A validated POWER time standard (`LST` or `UTC`).

## Value

A `list` object of values to be passed to a
[crul](https://CRAN.R-project.org/package=crul) object to query the
'POWER' 'API'.
