# Clear the Response Cache

Removes all cached responses from the cache directory. Only brapiR2's
own cache files are removed; anything else in the directory is left
alone.

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
con <- brapi_cache_enable(con, dir = tempfile("brapi_cache_"))
#> ✔ Caching enabled at /tmp/Rtmp1vXenZ/brapi_cache_82560a7e435 (TTL: 3600s)
brapi_cache_clear(con)
#> ℹ Cache is already empty.
```
