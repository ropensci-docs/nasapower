# Send Query to POWER Data API

Sends the query to the POWER data API to retrieve data.

## Usage

``` r
.send_query(.query_list, .url)
```

## Arguments

- .query_list:

  A query list created by
  [`.build_query()`](https://docs.ropensci.org/nasapower/reference/dot-build_query.md)

- .url:

  A character string of the URL to be used for the API query

## Value

The HTTP response object from the POWER server containing either an
error message or the requested data.
