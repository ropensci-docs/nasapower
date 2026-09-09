# Check User Inputs for get_power for Validity

Check User Inputs for get_power for Validity

## Usage

``` r
.check_inputs(
  lonlat,
  pars,
  site_elevation,
  temporal_api,
  wind_elevation,
  wind_surface
)
```

## Arguments

- lonlat:

  A numeric vector of geographic coordinates for a cell or region
  entered as x, y (longitude, latitude) coordinates. See argument
  details for more.

- pars:

  case-insensitive character vector of solar, meteorological or
  climatology parameters to download. When requesting a single point of
  x, y coordinates, a maximum of twenty (20) `pars` can be specified at
  one time, for “daily”, “monthly” and “climatology” `temporal_api`s. If
  the `temporal_api` is specified as “hourly” only 15 `pars` can be
  specified in a single query. See `temporal_api` for more. These values
  are checked internally for validity before sending the query to the
  POWER API.

- site_elevation:

  A user-supplied value for elevation at a single point in metres. If
  provided this will return a corrected atmospheric pressure value
  adjusted to the elevation provided. Only used with `lonlat` as a
  single point of x, y coordinates, not for use with “global” or with a
  regional request.

- temporal_api:

  A case-insensitive character vector providing the temporal API
  end-point for data being queried, supported values are “hourly”,
  “daily”, “monthly” or “climatology”. Defaults to “daily”. See argument
  details for more.

- wind_elevation:

  A user-supplied value for elevation at a single point in metres. Wind
  Elevation values in Meters are required to be between 10 m and 300 m.
  Only used with `lonlat` as a single point of x, y coordinates, not for
  use with “global” or with a regional request. If this parameter is
  provided, the `wind_surface` parameter is required with the request,
  see <https://power.larc.nasa.gov/docs/methodology/meteorology/wind/>.

- wind_surface:

  A user-supplied wind surface for which the corrected wind-speed is to
  be supplied. See `wind-surface` section for more detail.

## Value

A list with validated (and possibly nulled) `site_elevation` and
`wind_elevation` values, so that side-effects are not silently lost.
