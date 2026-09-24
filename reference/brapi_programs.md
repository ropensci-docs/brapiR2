# List Breeding Programs

Retrieves a list of breeding programs from the BrAPI server.

## Usage

``` r
brapi_programs(con, ...)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- ...:

  Additional query parameters passed to the API (e.g.
  `commonCropName = "rice"`, `programName = "IRRI"`).

## Value

A tibble with one row per program.

## BrAPI endpoint

`GET /programs` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Core/Programs/Programs_GET_POST.yaml).

Query parameters the specification defines, which may be passed through
`...`:

`abbreviation`, `programType`.

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  brapi_programs(con)
  brapi_programs(con, commonCropName = "rice")
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> # A tibble: 0 × 0
# }
```
