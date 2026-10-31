# BrAPI Endpoints Covered by brapiR2

brapiR2 wraps 49 of the 138 retrieval endpoints the BrAPI v2.1
specification defines, across 32 of its 37 top-level entities. This
topic lists them by module, with the function that wraps each one.

## Details

Each function's own help page names its endpoint, links to the
specification, and lists the query parameters that endpoint accepts.
[`brapi_endpoints()`](https://docs.ropensci.org/brapiR2/reference/brapi_endpoints.md)
is a different thing: it asks a particular server which endpoints *it*
implements, which is usually a smaller set again.

## Core module

- `GET /lists`:

  [`brapi_lists()`](https://docs.ropensci.org/brapiR2/reference/brapi_lists.md)

- `GET /lists/{listDbId}`:

  [`brapi_list()`](https://docs.ropensci.org/brapiR2/reference/brapi_list.md)

- `GET /locations`:

  [`brapi_locations()`](https://docs.ropensci.org/brapiR2/reference/brapi_locations.md)

- `GET /locations/{locationDbId}`:

  [`brapi_location()`](https://docs.ropensci.org/brapiR2/reference/brapi_location.md)

- `GET /people`:

  [`brapi_people()`](https://docs.ropensci.org/brapiR2/reference/brapi_people.md)

- `GET /programs`:

  [`brapi_programs()`](https://docs.ropensci.org/brapiR2/reference/brapi_programs.md)

- `GET /programs/{programDbId}`:

  [`brapi_program()`](https://docs.ropensci.org/brapiR2/reference/brapi_program.md)

- `GET /seasons`:

  [`brapi_seasons()`](https://docs.ropensci.org/brapiR2/reference/brapi_seasons.md)

- `GET /serverinfo`:

  [`brapi_endpoints()`](https://docs.ropensci.org/brapiR2/reference/brapi_endpoints.md),
  [`brapi_ping()`](https://docs.ropensci.org/brapiR2/reference/brapi_ping.md),
  [`brapi_server_info()`](https://docs.ropensci.org/brapiR2/reference/brapi_server_info.md)

- `GET /studies`:

  [`brapi_studies()`](https://docs.ropensci.org/brapiR2/reference/brapi_studies.md)

- `GET /studies/{studyDbId}`:

  [`brapi_study()`](https://docs.ropensci.org/brapiR2/reference/brapi_study.md)

- `GET /trials`:

  [`brapi_trials()`](https://docs.ropensci.org/brapiR2/reference/brapi_trials.md)

- `GET /trials/{trialDbId}`:

  [`brapi_trial()`](https://docs.ropensci.org/brapiR2/reference/brapi_trial.md)

## Germplasm module

- `GET /attributes`:

  [`brapi_germplasm_attributes()`](https://docs.ropensci.org/brapiR2/reference/brapi_germplasm_attributes.md)

- `GET /crosses`:

  [`brapi_crosses()`](https://docs.ropensci.org/brapiR2/reference/brapi_crosses.md)

- `GET /crossingprojects`:

  [`brapi_crossing_projects()`](https://docs.ropensci.org/brapiR2/reference/brapi_crossing_projects.md)

- `GET /germplasm`:

  [`brapi_germplasm()`](https://docs.ropensci.org/brapiR2/reference/brapi_germplasm.md)

- `GET /germplasm/{germplasmDbId}`:

  [`brapi_germplasm_detail()`](https://docs.ropensci.org/brapiR2/reference/brapi_germplasm_detail.md)

- `GET /pedigree`:

  [`brapi_germplasm_pedigree()`](https://docs.ropensci.org/brapiR2/reference/brapi_germplasm_pedigree.md),
  [`brapi_germplasm_progeny()`](https://docs.ropensci.org/brapiR2/reference/brapi_germplasm_progeny.md),
  [`brapi_pedigree()`](https://docs.ropensci.org/brapiR2/reference/brapi_pedigree.md)

- `POST /search/germplasm`:

  [`brapi_search_germplasm()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_germplasm.md)

- `POST /search/pedigree`:

  [`brapi_search_pedigree()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_pedigree.md)

- `GET /seedlots`:

  [`brapi_seed_lots()`](https://docs.ropensci.org/brapiR2/reference/brapi_seed_lots.md)

## Phenotyping module

- `GET /events`:

  [`brapi_events()`](https://docs.ropensci.org/brapiR2/reference/brapi_events.md)

- `GET /images`:

  [`brapi_images()`](https://docs.ropensci.org/brapiR2/reference/brapi_images.md)

- `GET /methods`:

  [`brapi_methods()`](https://docs.ropensci.org/brapiR2/reference/brapi_methods.md)

- `GET /observations`:

  [`brapi_observations()`](https://docs.ropensci.org/brapiR2/reference/brapi_observations.md)

- `GET /observationunits`:

  [`brapi_observation_units()`](https://docs.ropensci.org/brapiR2/reference/brapi_observation_units.md)

- `GET /ontologies`:

  [`brapi_ontologies()`](https://docs.ropensci.org/brapiR2/reference/brapi_ontologies.md)

- `GET /ontologies/{ontologyDbId}`:

  [`brapi_ontology()`](https://docs.ropensci.org/brapiR2/reference/brapi_ontology.md)

- `GET /scales`:

  [`brapi_scales()`](https://docs.ropensci.org/brapiR2/reference/brapi_scales.md)

- `POST /search/observations`:

  [`brapi_search_observations()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_observations.md)

- `POST /search/variables`:

  [`brapi_search_variables()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_variables.md)

- `GET /traits`:

  [`brapi_traits()`](https://docs.ropensci.org/brapiR2/reference/brapi_traits.md)

- `GET /variables`:

  [`brapi_observation_variables()`](https://docs.ropensci.org/brapiR2/reference/brapi_observation_variables.md)

## Genotyping module

- `GET /allelematrix`:

  [`brapi_allele_matrix()`](https://docs.ropensci.org/brapiR2/reference/brapi_allele_matrix.md)

- `GET /calls`:

  [`brapi_calls()`](https://docs.ropensci.org/brapiR2/reference/brapi_calls.md)

- `GET /callsets`:

  [`brapi_call_sets()`](https://docs.ropensci.org/brapiR2/reference/brapi_call_sets.md)

- `GET /maps`:

  [`brapi_maps()`](https://docs.ropensci.org/brapiR2/reference/brapi_maps.md)

- `GET /maps/{mapDbId}`:

  [`brapi_map()`](https://docs.ropensci.org/brapiR2/reference/brapi_map.md)

- `GET /maps/{mapDbId}/linkagegroups`:

  [`brapi_map_linkage_groups()`](https://docs.ropensci.org/brapiR2/reference/brapi_map_linkage_groups.md)

- `GET /markerpositions`:

  [`brapi_marker_positions()`](https://docs.ropensci.org/brapiR2/reference/brapi_marker_positions.md)

- `GET /references`:

  [`brapi_references()`](https://docs.ropensci.org/brapiR2/reference/brapi_references.md)

- `GET /referencesets`:

  [`brapi_reference_sets()`](https://docs.ropensci.org/brapiR2/reference/brapi_reference_sets.md)

- `GET /samples`:

  [`brapi_samples()`](https://docs.ropensci.org/brapiR2/reference/brapi_samples.md)

- `POST /search/calls`:

  [`brapi_search_calls()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_calls.md)

- `POST /search/markerpositions`:

  [`brapi_search_marker_positions()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_marker_positions.md)

- `POST /search/variants`:

  [`brapi_search_variants()`](https://docs.ropensci.org/brapiR2/reference/brapi_search_variants.md)

- `GET /variants`:

  [`brapi_variants()`](https://docs.ropensci.org/brapiR2/reference/brapi_variants.md)

- `GET /variantsets`:

  [`brapi_variant_sets()`](https://docs.ropensci.org/brapiR2/reference/brapi_variant_sets.md)

## Not covered

Common Crop Names, Germplasm Attribute Values, Planned Crosses, Plates
and Vendor Samples have no wrapper. `POST` and `PUT` write endpoints are
out of scope by design.
[`brapi_get()`](https://docs.ropensci.org/brapiR2/reference/brapi_get.md)
and
[`brapi_post_search()`](https://docs.ropensci.org/brapiR2/reference/brapi_post_search.md)
reach anything not wrapped here.
