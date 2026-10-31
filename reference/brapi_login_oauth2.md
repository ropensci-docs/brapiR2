# Login to a BrAPI Server with OAuth 2.0

Performs the OAuth 2.0 client-credentials grant: posts the client ID and
secret, form-encoded, to the token endpoint and returns an updated
connection object with the Bearer token set. Interactive
(authorization-code) login is not supported.

## Usage

``` r
brapi_login_oauth2(
  con,
  client_id,
  client_secret,
  authorize_url = NULL,
  access_url
)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- client_id:

  Character. OAuth client ID.

- client_secret:

  Character. OAuth client secret.

- authorize_url:

  Deprecated and unused: the client-credentials grant only needs
  `access_url`. Supplying it gives a warning.

- access_url:

  Character. The token endpoint URL.

## Value

A new `brapi_con` object with the token populated.

## BrAPI endpoint

None. The token request goes to `access_url`, your identity provider's
OAuth 2.0 token endpoint, which is not part of the BrAPI specification.

## Examples

``` r
if (FALSE) { # \dontrun{
# Needs an OAuth 2.0 token endpoint and client credentials of your own;
# the public BrAPI test server has no OAuth server to run this against.
con <- brapi_connection("https://my-brapi-server.org")
con <- brapi_login_oauth2(
  con,
  client_id = Sys.getenv("BRAPI_CLIENT_ID"),
  client_secret = Sys.getenv("BRAPI_CLIENT_SECRET"),
  access_url = "https://auth.my-brapi-server.org/token"
)
con
} # }
```
