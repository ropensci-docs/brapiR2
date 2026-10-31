# List Studies

Retrieves studies (occurrences/environments), optionally filtered by
trial.

## Usage

``` r
brapi_studies(con, trialDbId = NULL, ...)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- trialDbId:

  Character or NULL. Filter by trial.

- ...:

  Additional query parameters.

## Value

A tibble with one row per study.

## BrAPI endpoint

`GET /studies` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Core/Studies/Studies_GET_POST.yaml).

Query parameters the specification defines, which may be passed through
`...`:

`studyType`, `locationDbId`, `seasonDbId`, `studyCode`, `studyPUI`,
`observationVariableDbId`, `active`, `sortBy`, `sortOrder`.

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  brapi_studies(con)
  brapi_studies(con, trialDbId = "trial1")
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> # A tibble: 1 × 29
#>   additionalInfo   externalReferences active commonCropName contacts  
#>   <list>           <list>             <lgl>  <chr>          <list>    
#> 1 <named list [1]> <list [1]>         TRUE   Tomatillo      <list [1]>
#> # ℹ 24 more variables: culturalPractices <chr>, dataLinks <list>,
#> #   documentationURL <chr>, endDate <chr>, environmentParameters <list>,
#> #   experimentalDesign <list>, growthFacility <list>, lastUpdate <list>,
#> #   license <chr>, locationDbId <chr>, locationName <chr>,
#> #   observationLevels <list>, observationUnitsDescription <chr>,
#> #   seasons <list>, startDate <chr>, studyCode <chr>, studyDescription <chr>,
#> #   studyName <chr>, studyPUI <chr>, studyType <chr>, trialDbId <chr>, …
# }
```
