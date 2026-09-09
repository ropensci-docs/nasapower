# Get Connection Timeout Option

Retrieves the connection timeout value for POWER API requests from the
`nasapower.timeout.connect` option, falling back to a default of `5L`
seconds if not set.

## Usage

``` r
.get_timeout_connect()
```

## Value

An integer giving the connection timeout in seconds.

## Examples

``` r
# Use default
.get_timeout_connect()
#> Error in .get_timeout_connect(): could not find function ".get_timeout_connect"

# Override via option
options(nasapower.timeout.connect = 10L)
.get_timeout_connect()
#> Error in .get_timeout_connect(): could not find function ".get_timeout_connect"
```
