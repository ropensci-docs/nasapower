# Match Wind Surface Aliases for Validity

Validates and matches surface type aliases against allowed values.

## Usage

``` r
.match_surface_alias(x)
```

## Arguments

- x:

  A character string representing a surface type alias.

## Value

The matched surface alias (lowercased), or NULL if input is NULL. The
POWER API accepts case-insensitive surface aliases
