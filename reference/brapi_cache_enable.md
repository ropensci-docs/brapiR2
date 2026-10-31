# Enable Response Caching

Returns a new connection object with caching enabled. Cached responses
are stored as JSON files in the specified directory, keyed by URL, query
parameters and (hashed) token, so connections with different credentials
never share an entry.

## Usage

``` r
brapi_cache_enable(con, dir = NULL, ttl = 3600)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- dir:

  Character. Directory to store cached responses. Defaults to R's
  per-user cache directory for brapiR2,
  `tools::R_user_dir("brapiR2", "cache")`.

- ttl:

  Numeric. Time-to-live for cached entries in seconds. Default 3600 (1
  hour).

## Value

A new `brapi_con` object with caching configured.

## Examples

``` r
con <- brapi_connection("https://test-server.brapi.org")
con <- brapi_cache_enable(con, dir = tempfile("brapi_cache_"), ttl = 7200)
#> ✔ Caching enabled at /tmp/Rtmp1vXenZ/brapi_cache_82549d6cae9 (TTL: 7200s)
con
#> 
#> ── BrAPI Connection 
#> • Server: <https://test-server.brapi.org>
#> • Version: v2
#> • Auth: ✗ no token
#> • Page size: 1000
#> • Timeout: 120s
#> • Cache: enabled (/tmp/Rtmp1vXenZ/brapi_cache_82549d6cae9)
```
