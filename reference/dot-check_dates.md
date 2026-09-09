# Check dates for validity when querying the API

Validates user entered dates against `lonlat` and `temporal_api` values

## Usage

``` r
.check_dates(dates, lonlat, temporal_api)
```

## Arguments

- dates:

  User entered `dates` value.

- lonlat:

  User entered `lonlat` value.

- temporal_api:

  User entered `temporal_api` value.

## Value

Validated dates in a list for use in `.build_query`.
