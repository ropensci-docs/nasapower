# Query the POWER API for Detailed Information on Wind Type Surfaces

Queries the POWER API returning detailed information on all (or just
one) wind elevation surface alias and attribute information.

## Usage

``` r
query_surfaces(surface_alias = NULL)
```

## Arguments

- surface_alias:

  An optional character vector providing a wind surface alias available
  from the POWER API. All values are returned if not provided.

## Value

A list object of information for the requested wind surface(s).

## Author

Adam H. Sparks, <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()
# Fetch all wind surface information
query_surfaces()

# Fetch surface information for "airportgrass"
query_surfaces(surface_alias = "airportgrass")
}
```
