# Ping a BrAPI Server

Tests whether the BrAPI server is reachable and responding.

## Usage

``` r
brapi_ping(con, ...)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- ...:

  Additional query parameters.

## Value

Logical, invisibly. `TRUE` if `/serverinfo` answers with HTTP 200 and a
JSON body, or with 401/403 (the server is up but needs authentication);
`FALSE` otherwise. The HTTP status is attached as the `"status"`
attribute (`NA` if the server could not be reached).

## Details

A ping uses a timeout of at most 10 seconds and doesn't retry, so an
unreachable server is reported quickly.

## BrAPI endpoint

`GET /serverinfo` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Core/ServerInfo/ServerInfo_GET.yaml).

Query parameters the specification defines, which may be passed through
`...`:

`contentType`, `dataType`.

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
brapi_ping(con)
#> ✔ Server <https://test-server.brapi.org> is reachable.
# }
```
