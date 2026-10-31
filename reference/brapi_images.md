# List Images

List Images

## Usage

``` r
brapi_images(con, ...)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- ...:

  Additional query parameters.

## Value

A tibble with one row per image record.

## BrAPI endpoint

`GET /images` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Phenotyping/Images/Images_GET_POST.yaml).

Query parameters the specification defines, which may be passed through
`...`:

`imageDbId`, `imageName`, `observationUnitDbId`, `observationDbId`,
`descriptiveOntologyTerm`.

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  brapi_images(con)
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> # A tibble: 2 × 17
#>   additionalInfo copyright description descriptiveOntologyT…¹ externalReferences
#>   <list>         <chr>     <chr>       <list>                 <list>            
#> 1 <named list>   Copyrigh… This is an… <list [2]>             <list [1]>        
#> 2 <named list>   Copyrigh… This is an… <list [2]>             <list [1]>        
#> # ℹ abbreviated name: ¹​descriptiveOntologyTerms
#> # ℹ 12 more variables: imageFileName <chr>, imageFileSize <int>,
#> #   imageHeight <int>, imageLocation <list>, imageName <chr>,
#> #   imageTimeStamp <chr>, imageURL <chr>, imageWidth <int>, mimeType <chr>,
#> #   observationDbIds <lgl>, observationUnitDbId <chr>, imageDbId <chr>
# }
```
