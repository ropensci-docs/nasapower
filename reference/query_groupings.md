# Query the POWER API for Detailed Information on Available Parameter Groupings

Queries the POWER API returning detailed information on available
parameter groupings. Results are grouped by community followed by
temporal API, or if `global = TRUE`, grouped by climatology then by
available parameter types.

## Usage

``` r
query_groupings(global = FALSE)
```

## Arguments

- global:

  Boolean; should the query return global parameter groupings and
  attribute information? Defaults to `FALSE`, returning details for
  point data.

## Value

A list object of information on parameter groupings in the POWER API.

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Fetch groupings for parameters
query_groupings()

# Fetch groupings for global parameters
query_groupings(global = TRUE)
}
```
