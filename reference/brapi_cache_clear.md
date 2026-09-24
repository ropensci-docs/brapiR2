# Clear the Response Cache

Removes all cached responses from the cache directory.

## Usage

``` r
brapi_cache_clear(con)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object with caching enabled.

## Value

Invisibly returns `con`.

## Examples

``` r
con <- brapi_connection("https://test-server.brapi.org")
con <- brapi_cache_enable(con, dir = tempdir())
#> ✔ Caching enabled at /tmp/RtmpoBHVsA (TTL: 3600s)
brapi_cache_clear(con)
#> Warning: cannot remove file '/tmp/RtmpoBHVsA/bslib-47a5ad1736412c5c3f9dcbdae6154908', reason 'Directory not empty'
#> Warning: cannot remove file '/tmp/RtmpoBHVsA/downlit', reason 'Directory not empty'
#> ✔ Cleared 8 cached response(s).
```
