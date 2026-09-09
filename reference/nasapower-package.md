# nasapower: NASA POWER API Client

An API client for NASA POWER global meteorology, surface solar energy
and climatology data API. POWER (Prediction Of Worldwide Energy
Resources) data are freely available for download with varying spatial
resolutions dependent on the original data and with several temporal
resolutions depending on the POWER parameter and community. This work is
funded through the NASA Earth Science Directorate Applied Science
Program. For more on the data themselves, the methodologies used in
creating, a web-based data viewer and web access, please see
<https://power.larc.nasa.gov/>.

## See also

Useful links:

- <https://codeberg.org/ropensci/nasapower>

- <https://docs.ropensci.org/nasapower/>

- Report bugs at <https://codeberg.org/ropensci/nasapower/issues>

## Author

**Maintainer**: Adam H. Sparks <adamhsparks@gmail.com>
([ORCID](https://orcid.org/0000-0002-0061-8359))

Authors:

- Adam H. Sparks <adamhsparks@gmail.com>
  ([ORCID](https://orcid.org/0000-0002-0061-8359))

Other contributors:

- Scott Chamberlain <myrmecocystus@gmail.com>
  ([ORCID](https://orcid.org/0000-0003-1444-9135)) (Scott Chamberlain
  reviewed nasapower for rOpenSci, see
  \<https://github.com/ropensci/software-review/issues/155\>.)
  \[reviewer\]

- Hazel Kavili (Hazel Kavili reviewed nasapower for rOpenSci, see
  \<https://github.com/ropensci/software-review/issues/155\>.)
  \[reviewer\]

- Alison Boyer (Alison Boyer reviewed nasapower for rOpenSci, see
  \<https://github.com/ropensci/software-review/issues/155\>.)
  \[reviewer\]

- Fernando Miguez <femiguez@iastate.edu>
  ([ORCID](https://orcid.org/0000-0002-4627-8329)) (Fernando Miguez
  provided assistance in identifying improper missing value handling in
  the POWER data, see \<https://github.com/femiguez/apsimx/pull/26\>.)
  \[contributor\]

- Maëlle Salmon ([ORCID](https://orcid.org/0000-0002-2815-0399)) (Maëlle
  Salmon contributed a patch to fix issues with using the R package,
  'vcr', for testing the API queries, see
  \<https://github.com/ropensci/nasapower/pull/64\>.) \[contributor\]

- Phillip D. Alderman <phillip.alderman@okstate.edu>
  ([ORCID](https://orcid.org/0000-0003-1467-2337)) (Phillip Alderman
  contributed a patch to fix an issue with, 'The \`file\` argument of
  \`vroom()\` must use \`I()\` for literal data as of vroom 1.5.0.', see
  \<https://github.com/ropensci/nasapower/pull/67\>.) \[contributor\]

- Aleksandar Blagotić <alex@rapporter.net> (Author of the CRAN package
  'rapportools', from which the '.is_boolean()' was derived.)
  \[contributor, copyright holder\]

- Gergely Daróczi <daroczig@rapporter.net> (Author of the CRAN package
  'rapportools', from which the '.is_boolean()' was derived.)
  \[contributor, copyright holder\]

- Curtin University ([ROR](https://ror.org/02n415q13))
  (http://www.curtin.edu.au/) \[copyright holder\]
