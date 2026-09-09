# Query the POWER API for Detailed Information on Available Parameters

Queries the POWER API returning detailed information on available
parameters. For a list of all available parameters, see `parameters`.

## Usage

``` r
query_parameters(
  community = NULL,
  pars = NULL,
  temporal_api = NULL,
  metadata = FALSE
)
```

## Arguments

- community:

  An optional character vector providing community name: "ag", "sb", or
  "re".

- pars:

  An optional character string of a single solar, meteorological, or
  climatology parameter to query. If not provided, all parameters are
  returned.

- temporal_api:

  An optional character vector indicating the temporal API endpoint for
  data being queried. Supported values are "hourly", "daily", "monthly",
  or "climatology".

- metadata:

  Boolean; retrieve extra parameter metadata? This is only applicable if
  you supply both `community` and `temporal_api`; otherwise it will be
  ignored. Defaults to `FALSE`.

## Value

A list object of information for the requested parameter(s),
community(ies), and temporal API(s).

## Argument details for `temporal_api`

There are four valid values:

- hourly:

  The hourly average of parameters by hour, day, month, and year.

- daily:

  The daily average of parameters by day, month, and year.

- monthly:

  The monthly average of parameters by month and year.

- climatology:

  Parameters as 22-year climatologies (solar) and 30-year climatologies
  (meteorology); includes period climatology and monthly average,
  maximum, and/or minimum values.

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Fetch complete attribute information for "T2M"
query_parameters(pars = "T2M")

# Fetch temporal and community-specific attribute information
# for "T2M" in the "ag" community for the "hourly" temporal API
query_parameters(
  pars = "T2M",
  community = "ag",
  temporal_api = "hourly"
)

# Fetch all parameters in the "ag" community for "hourly" temporal API
query_parameters(
  community = "ag",
  temporal_api = "hourly"
)
}
```
