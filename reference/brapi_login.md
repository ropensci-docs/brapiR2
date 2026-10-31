# Login to a BrAPI Server with Username and Password

Authenticates using the BrAPI `/token` endpoint and returns an updated
connection object with the Bearer token set.

## Usage

``` r
brapi_login(con, username, password)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- username:

  Character. Your username.

- password:

  Character. Your password.

## Value

A new `brapi_con` object with the token populated.

## BrAPI endpoint

`POST /token`. This is not part of the BrAPI v2.1 specification: it is a
server extension, implemented by Breedbase and by the BrAPI test server.
Servers without it need
[`brapi_login_oauth2()`](https://docs.ropensci.org/brapiR2/reference/brapi_login_oauth2.md)
or
[`brapi_set_token()`](https://docs.ropensci.org/brapiR2/reference/brapi_set_token.md)
instead.

## See also

The "Handling Credentials Safely" section of
[`vignette("brapiR2")`](https://docs.ropensci.org/brapiR2/articles/brapiR2.md)
for how to keep `username`/`password` out of your script, using
`.Renviron` or the keyring package.

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  con <- brapi_login(con, "brapi_reader", "brapi_reader")
  con
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> ✔ Logged in to <https://test-server.brapi.org>
#> 
#> ── BrAPI Connection 
#> • Server: <https://test-server.brapi.org>
#> • Version: v2
#> • Auth: ✓ authenticated
#> • Page size: 1000
#> • Timeout: 120s
#> • Cache: disabled
# }
```
