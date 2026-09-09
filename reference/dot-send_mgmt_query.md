# Send Query to POWER Management API

Sends the query to the POWER management API.

## Usage

``` r
.send_mgmt_query(.url)
```

## Arguments

- .url:

  A character string of the URL to be used for the API query.

## Value

The HTTP response object from the POWER server containing either an
error message or the requested data.

## Details

Note: The management API endpoints do not accept parameters.
