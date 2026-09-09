# Get Request Timeout Option

Retrieves the timeout value for POWER API requests from the
`nasapower.timeout` option, falling back to a default of `10L` seconds
if not set.

## Usage

``` r
.get_timeout()
```

## Value

An integer giving the timeout in seconds.

## Examples

``` r
# Use default
.get_timeout()
#> Error in .get_timeout(): could not find function ".get_timeout"

# Override via option
options(nasapower.timeout = 60L)
.get_timeout()
#> Error in .get_timeout(): could not find function ".get_timeout"
```
