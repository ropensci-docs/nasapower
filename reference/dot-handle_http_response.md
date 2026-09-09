# Handle HTTP Response Errors

Validates HTTP response status codes and extracts error messages.

## Usage

``` r
.handle_http_response(response)
```

## Arguments

- response:

  A response object from `crul::HttpClient$get()`.

## Value

Invisibly returns the response if status code is \< 400, otherwise
throws an error.
