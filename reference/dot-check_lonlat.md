# Check user-supplied `lonlat` for validity when querying API

Validates user-entered `lonlat` values.

## Usage

``` r
.check_lonlat(lonlat)
```

## Arguments

- lonlat:

  User entered `lonlat` value.

## Value

A list called `lonlat_identifier` for use in
[`.build_query()`](https://docs.ropensci.org/nasapower/reference/dot-build_query.md).
