# Get a Single Study by ID

Get a Single Study by ID

## Usage

``` r
brapi_study(con, studyDbId)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- studyDbId:

  Character. The unique study identifier.

## Value

A single-row tibble with study metadata.

## BrAPI endpoint

`GET /studies/{studyDbId}` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Core/Studies/Studies_StudyDbId_GET_PUT.yaml).

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  brapi_study(con, "study1")
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> # A tibble: 1 × 8
#>   dataFormat    description     fileFormat name  provenance scientificType url  
#>   <chr>         <chr>           <chr>      <chr> <chr>      <chr>          <chr>
#> 1 Image Archive Raw drone imag… applicati… imag… Image Pro… Environmental  http…
#> # ℹ 1 more variable: version <chr>
# }
```
