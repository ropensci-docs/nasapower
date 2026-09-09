# Check if Object is a Boolean

Checks if provided object is a Boolean (i.e., a length-one logical
vector).

## Usage

``` r
.is_boolean(x)
```

## Arguments

- x:

  An object to check.

## Value

A logical value indicating whether the provided object is a Boolean.

## Note

Taken from
<https://github.com/Rapporter/rapportools/blob/master/R/utils.R>

## Examples

``` r
.is_boolean(TRUE) # [1] TRUE
#> Error in .is_boolean(TRUE): could not find function ".is_boolean"
.is_boolean(1) # [1] FALSE
#> Error in .is_boolean(1): could not find function ".is_boolean"
```
