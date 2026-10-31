# Get Study Data in Wide Format

A convenience function that fetches a study's observations and pivots
them into a wide-format tibble with one row per observation unit and one
column per trait — ready for analysis.

## Usage

``` r
brapi_study_data(con, studyDbId, fallback = FALSE)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- studyDbId:

  Character. The unique study identifier.

- fallback:

  Logical. If the filtered request returns no observations, fetch all
  observations on the server and filter them to `studyDbId` locally.
  Default `FALSE`.

## Value

A wide-format tibble with the observation unit, germplasm and study
identifier columns the server provides, and one character column per
observed trait holding its values. A cell with repeated measurements is
a list of them.

## Details

Some servers ignore the `studyDbId` filter on `/observations` and return
nothing for it; the public BrAPI test server (test-server.brapi.org) is
one. Set `fallback = TRUE` to fetch every observation on such a server
and filter them locally. That can mean a very large download on a
production server, so it is off by default.

## BrAPI endpoint

`GET /observations`, filtered by `studyDbId`, and with no filter when
`fallback = TRUE` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Phenotyping/Observations/Observations_GET_POST_PUT.yaml).

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  # The test server ignores the studyDbId filter, so opt in to the fallback
  data <- brapi_study_data(con, "study1", fallback = TRUE)
  head(data)
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> # A tibble: 2 × 6
#>   observationUnitDbId observationUnitName germplasmDbId germplasmName  studyDbId
#>   <chr>               <chr>               <chr>         <chr>          <chr>    
#> 1 observation_unit1   Plot 1              germplasm1    Tomatillo Fan… study1   
#> 2 observation_unit2   Plot 2              germplasm2    Tomatillo Fan… study1   
#> # ℹ 1 more variable: `Corn Stalk Height` <list>
# }
```
