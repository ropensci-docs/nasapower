# Get NASA POWER data from the POWER API

Get POWER global meteorology and surface solar energy climatology data
and return a tidy data frame
[tibble](https://CRAN.R-project.org/package=tibble) object. All options
offered by the official POWER API are supported. Requests are formed to
submit one request per point. There is no need to make synchronous
requests for multiple parameters for a single point or regional request.
See section on “Rate Limiting” for more.

## Usage

``` r
get_power(
  community,
  pars,
  lonlat,
  temporal_api = "daily",
  dates = NULL,
  site_elevation = NULL,
  wind_elevation = NULL,
  wind_surface = NULL,
  time_standard = "LST"
)
```

## Arguments

- community:

  A case-insensitive character vector providing community name: “AG”,
  “RE” or “SB”. See argument details for more.

- pars:

  case-insensitive character vector of solar, meteorological or
  climatology parameters to download. When requesting a single point of
  x, y coordinates, a maximum of twenty (20) `pars` can be specified at
  one time, for “daily”, “monthly” and “climatology” `temporal_api`s. If
  the `temporal_api` is specified as “hourly” only 15 `pars` can be
  specified in a single query. See `temporal_api` for more. These values
  are checked internally for validity before sending the query to the
  POWER API.

- lonlat:

  A numeric vector of geographic coordinates for a cell or region
  entered as x, y (longitude, latitude) coordinates. See argument
  details for more.

- temporal_api:

  A case-insensitive character vector providing the temporal API
  end-point for data being queried, supported values are “hourly”,
  “daily”, “monthly” or “climatology”. Defaults to “daily”. See argument
  details for more.

- dates:

  A character vector of start and end dates in that order,  
  *e.g.*, `dates = c("1983-01-01", "2017-12-31")`. Not used when  
  `temporal_api` is set to “climatology”. See argument details for more.

- site_elevation:

  A user-supplied value for elevation at a single point in metres. If
  provided this will return a corrected atmospheric pressure value
  adjusted to the elevation provided. Only used with `lonlat` as a
  single point of x, y coordinates, not for use with “global” or with a
  regional request.

- wind_elevation:

  A user-supplied value for elevation at a single point in metres. Wind
  elevation values are required to be between 10 and 300 metres. Only
  used with `lonlat` as a single point of x, y coordinates, not for use
  with “global” or with a regional request. If this parameter is
  provided, the `wind_surface` parameter is required with the request,
  see <https://power.larc.nasa.gov/docs/methodology/meteorology/wind/>.

- wind_surface:

  A user-supplied wind surface for which the corrected wind-speed is to
  be supplied. See `wind-surface` section for more detail.

- time_standard:

  POWER provides two different time standards.

  - Universal Time Coordinated (UTC): is the standard time- measure that
    used by the world.

  - Local Solar Time (LST): A 15 degree swath that represents solar noon
    at the middle longitude of the swath. Defaults to `LST`.

## Value

A data frame as a `POWER.Info` class, an extension of the
[tibble](https://CRAN.R-project.org/package=tibble), object of POWER
data including location, dates (not including “climatology”) and
requested parameters; a decorative header of metadata is included in
this object.

## Note

The associated metadata shown in the decorative header are not saved if
the data are exported to a file format other than a native R data
format, *e.g.*, .Rdata, .rda or .rds.

## Argument details for “community”

There are three valid values, one must be supplied. This will affect the
units of the parameter and the temporal display of time series data.

- ag:

  Provides access to the Agroclimatology Archive, which contains
  industry-friendly parameters formatted for input to crop models.

- sb:

  Provides access to the Sustainable Buildings Archive, which contains
  industry-friendly parameters for the buildings community to include
  parameters in multi-year monthly averages.

- re:

  Provides access to the Renewable Energy Archive, which contains
  parameters specifically tailored to assist in the design of solar and
  wind powered renewable energy systems.

## Argument details for `temporal_api`

There are four valid values.

- hourly:

  The hourly average of `pars` by hour, day, month and year, the time
  zone is LST by default.

- daily:

  The daily average of `pars` by day, month and year.

- monthly:

  The monthly average of `pars` by month and year.

- climatology:

  Provide parameters as 22-year climatologies (solar) and 30-year
  climatologies (meteorology); the period climatology and monthly
  average, maximum, and/or minimum values.

## Argument details for `lonlat`

- For a single point:

  To get a specific cell, 1/2 x 1/2 degree, supply a length-two numeric
  vector giving the decimal degree longitude and latitude in that order
  for data to download,  
  *e.g.*, `lonlat = c(-179.5, -89.5)`.

- For regional coverage:

  To get a region, supply a length-four numeric vector as lower left
  (lon, lat) and upper right (lon, lat) coordinates, *e.g.*,
  `lonlat = c(xmin, ymin, xmax, ymax)` in that order for a given region,
  *e.g.*, a bounding box for the south western corner of Australia:
  `lonlat = c(112.5, -55.5, 115.5, -50.5)`. \*Maximum area processed is
  4.5 x 4.5 degrees (100 points).

- For global coverage:

  To get global coverage for “climatology”, supply “global” while also
  specifying “climatology” for the `temporal_api`.

## Argument details for `dates`

if one date only is provided, it will be treated as both the start date
and the end date and only a single day's values will be returned,
*e.g.*, `dates = "1983-01-01"`. When `temporal_api` is set to “MONTHLY”,
use only two year values (YYYY), *e.g.* `dates = c(1983, 2010)`. This
argument should not be used when `temporal_api` is set to “climatology”
and will be ignored if set.

## `wind_surface`

There are 17 surfaces that may be used for corrected wind-speed values
using the following equation: \$\$WSC\_{hgt} = WS\_{10m} \times
(\frac{hgt}{WS\_{50m}})^\alpha\$\$ Valid surface types are described
here.

- vegtype_1:

  35-m broadleaf-evergreen trees (70% coverage)

- vegtype_2:

  20-m broadleaf-deciduous trees (75% coverage)

- vegtype_3:

  20-m broadleaf and needleleaf trees (75% coverage)

- vegtype_4:

  17-m needleleaf-evergreen trees (75% coverage)

- vegtype_5:

  14-m needleleaf-deciduous trees (50% coverage)

- vegtype_6:

  Savanna:18-m broadleaf trees (30%) && groundcover

- vegtype_7:

  0.6-m perennial groundcover (100%)

- vegtype_8:

  0.5-m broadleaf shrubs (variable %) && groundcover

- vegtype_9:

  0.5-m broadleaf shrubs (10%) with bare soil

- vegtype_10:

  Tundra: 0.6-m trees/shrubs (variable %) && groundcover

- vegtype_11:

  Rough bare soil

- vegtype_12:

  Crop: 20-m broadleaf-deciduous trees (10%) && wheat

- vegtype_20:

  Rough glacial snow/ice

- seaice:

  Smooth sea ice

- openwater:

  Open water

- airportice:

  Airport: flat ice/snow

- airportgrass:

  Airport: flat rough grass

## Rate limiting

The POWER API endpoints limit queries to prevent server overloads due to
repetitive and rapid requests. If you find that the API is throttling
your queries, I suggest that you investigate the use of `limit_rate()`
from [ratelimitr](https://CRAN.R-project.org/package=ratelimitr) to
create self-limiting functions that will respect the rate limits that
the API has in place. It is considered best practice to check the [POWER
website](https://power.larc.nasa.gov/docs/services/api/) for the latest
rate limits as they differ between temporal APIs and may change over
time as the project matures.

## References

<https://power.larc.nasa.gov/docs/methodology/>
<https://power.larc.nasa.gov>

## Author

Adam H. Sparks <adamhsparks@gmail.com>

## Examples

``` r
if (FALSE) { # interactive()

# Fetch daily "AG" community temperature, relative humidity and
# precipitation for January 1 1985 at Kingsthorpe, Queensland, Australia
ag_d <- get_power(
  community = "AG",
  lonlat = c(151.81, -27.48),
  pars = c("RH2M", "T2M", "PRECTOTCORR"),
  dates = "1985-01-01",
  temporal_api = "daily"
)

ag_d

# Fetch single point climatology for air temperature
ag_c_point <- get_power(
  community = "AG",
  pars = "T2M",
  c(151.81, -27.48),
  temporal_api = "climatology"
)

ag_c_point

# Fetch interannual solar cooking parameters for a given region
interannual_clrsky <- get_power(
  community = "re",
  lonlat = c(150.5, -28.5, 153.5, -25.5),
  dates = c("1984", "1985"),
  temporal_api = "monthly",
  pars = "CLRSKY_SFC_SW_DWN"
)

interannual_allsky <- get_power(
  community = "re",
  lonlat = c(150.5, -28.5, 153.5, -25.5),
  dates = c("1984", "1985"),
  temporal_api = "monthly",
  pars = "ALLSKY_SFC_SW_DWN"
)

interannual_list <- list(interannual_clrsky, interannual_allsky)

interannual_re <- do.call("rbind", interannual_list)

interannual_re
}
```
