# Get a Single List by ID, With Its Contents

Unlike
[`brapi_lists()`](https://docs.ropensci.org/brapiR2/reference/brapi_lists.md),
which returns only list metadata, this returns a single list together
with its members in the `data` list-column. `listType` says what the
members are (for example `"germplasm"`).

## Usage

``` r
brapi_list(con, listDbId)
```

## Arguments

- con:

  A
  [`brapi_connection()`](https://docs.ropensci.org/brapiR2/reference/brapi_connection.md)
  object.

- listDbId:

  Character. The unique list identifier.

## Value

A single-row tibble of list metadata, with the list's members as a
character vector in the `data` list-column.

## BrAPI endpoint

`GET /lists/{listDbId}` - see the [v2.1
specification](https://github.com/plantbreeding/BrAPI/blob/V2.1/Specification/BrAPI-Core/Lists/Lists_ListDbId_GET_PUT.yaml).

## Examples

``` r
# \donttest{
con <- brapi_connection("https://test-server.brapi.org")
if (brapi_ping(con)) {
  lst <- brapi_list(con, "list1")
  lst$data[[1]]
}
#> ✔ Server <https://test-server.brapi.org> is reachable.
#> [1] "germ1" "germ2" "germ3"
# }
```
