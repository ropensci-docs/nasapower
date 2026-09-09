# Check Pars for Validity When Querying API

Validates user entered `pars` values against `temporal_api` values.

## Usage

``` r
.check_pars(pars, community, temporal_api)
```

## Arguments

- pars:

  User entered `pars` value.

- community:

  User entered `community` value.

- temporal_api:

  User entered `temporal_api` value.

## Value

Validated a collapsed string of `pars` for use in
[.build_query](https://docs.ropensci.org/nasapower/reference/dot-build_query.md).
