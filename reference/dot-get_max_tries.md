# Get Max Tries Option

Retrieves the maximum number of request attempts for POWER API requests
from the `nasapower.max_tries` option, falling back to a default of `6L`
if not set.

## Usage

``` r
.get_max_tries()
```

## Value

An integer giving the maximum number of attempts.

## Examples

``` r
# Use default
.get_max_tries()
#> Error in .get_max_tries(): could not find function ".get_max_tries"

# Override via option
options(nasapower.max_tries = 3L)
.get_max_tries()
#> Error in .get_max_tries(): could not find function ".get_max_tries"
```
