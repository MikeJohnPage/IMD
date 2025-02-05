
<!-- README.md is generated from README.Rmd. Please edit that file -->

# IMD <img src='man/figures/logo.png' align="right" height="150" /></a>

<!-- badges: start -->

[![Project Status: Active – The project has reached a stable, usable
state and is being actively
developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)
[![CRAN
status](https://www.r-pkg.org/badges/version/IMD)](https://cran.r-project.org/package=IMD)
<!-- badges: end -->

The `IMD` package provides easy access to the Indices of Multiple
Deprivation for the UK’s nations at various geographical levels:

-   England: Lower Layer Super Output Area (LSOA), Middle Layer Super
    Output Area (MSOA), Ward, and Local Authority
-   Wales: LSOA, MSOA, Ward, and Local Authority
-   Scotland: Data Zone, Intermediate Zone, and Council Area
-   Northern Ireland: Super Output Area and Local Government District

## Installation

Install the released version of `IMD` from
[CRAN](https://cran.r-project.org/package=IMD):

``` r
install.packages("IMD")
```

Alternatively, you can install the development version from
[GitHub](https://github.com/) with:

``` r
# install.packages("devtools")
devtools::install_github("matthewgthomas/IMD")
```

## Usage

The `IMD` package provides several datasets for the IMD in each UK
nation:

### England

-   Lower Layer Super Output Areas: `IMD::imd_england_lsoa`
-   Middle Layer Super Output Areas: `IMD::imd_england_msoa`
-   Wards: `IMD::imd_england_ward`
-   Local Authorities: `IMD::imd_england_lad`

**Sub-domains of deprivation** are also available for England. These
include two in the Education domain (‘children and young people’ and
‘adult skills’), two for the Barriers domain (‘geographical barriers’
and ‘wider barriers’), and two for the Living Environment domain
(‘indoors’ and ‘outdoors’)

-   Sub-domains for LSOAs: `IMD::imd_england_lsoa_subdomains`
-   Sub-domains for MSOAs: `IMD::imd_england_msoa_subdomains`
-   Sub-domains for wards: `IMD::imd_england_ward_subdomains`
-   Sub-domains for Local Authorities: `IMD::imd_england_lad_subdomains`

### Wales

-   Lower Layer Super Output Areas: `IMD::imd_wales_lsoa`
-   Middle Layer Super Output Areas: `IMD::imd_wales_msoa`
-   Wards: `IMD::imd_wales_ward`
-   Local Authorities: `IMD::imd_wales_lad`

### Scotland

-   Data Zones: `IMD::imd_scotland_dz`
-   Intermediate Zones: `IMD::imd_scotland_iz`
-   Council Areas: `IMD::imd_scotland_lad`

### Northern Ireland

-   Super Output Areas: `IMD::imd_northern_ireland_soa`
-   Local Government Districts: `IMD::imd_northern_ireland_lad`

### Composite 2020 UK Index of Multiple Deprivation

We have also included the [composite 2020 UK Index of Multiple
Deprivation](https://github.com/mysociety/composite_uk_imd) produced by
mySociety, allowing comparison of deprivation across UK nations. For
more information about how and when to use this version of the IMD, see
[their
README](https://github.com/mysociety/composite_uk_imd/blob/master/readme.md).

Rather than providing a copy of this data, the `IMD` package loads the
data hosted on mySociety’s GitHub. To load these files, run the
following code:

``` r
imd_uk <- load_composite_imd(nation = "E")
```

This function defaults to loading the England-focused composite index;
change the `nation` parameter to the first letter of one of the devolved
UK nations to load the other versions.

## Example

How many wards in Wales are there with the 100% of the population living
in areas classified as among the most deprived?

``` r
library(IMD)

imd_wales_ward |> 
  dplyr::filter(Extent == 1) |> 
  dplyr::count()
#> # A tibble: 1 x 1
#>       n
#>   <int>
#> 1    14
```

## Accessing the data for non-R users

We’ve provided `.csv` files for each geographical area in each nation:

### England

-   Lower Layer Super Output Areas:
    [imd\_england\_lsoa.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_lsoa.csv)
-   Middle Layer Super Output Areas:
    [imd\_england\_msoa.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_msoa.csv)
-   Wards:
    [imd\_england\_ward.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_ward.csv)
-   Local Authorities:
    [imd\_england\_lad.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_lad.csv)

**Sub-domains of deprivation** are also available for England. These
include two in the Education domain (‘children and young people’ and
‘adult skills’), two for the Barriers domain (‘geographical barriers’
and ‘wider barriers’), and two for the Living Environment domain
(‘indoors’ and ‘outdoors’)

-   Sub-domains for LSOAs:
    [imd\_england\_lsoa\_subdomains.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_lsoa_subdomains.csv)
-   Sub-domains for MSOAs:
    [imd\_england\_msoa\_subdomains.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_msoa_subdomains.csv)
-   Sub-domains for wards:
    [imd\_england\_ward\_subdomains.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_ward_subdomains.csv)
-   Sub-domains for Local Authorities:
    [imd\_england\_lad\_subdomains.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_england_lad_subdomains.csv)

### Wales

-   Lower Layer Super Output Areas:
    [imd\_wales\_lsoa.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_wales_lsoa.csv)
-   Middle Layer Super Output Areas:
    [imd\_wales\_msoa.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_wales_msoa.csv)
-   Wards:
    [imd\_wales\_ward.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_wales_ward.csv)
-   Local Authorities:
    [imd\_wales\_lad.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_wales_lad.csv)

### Scotland

-   Data Zones:
    [imd\_scotland\_dz.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_scotland_dz.csv)
-   Intermediate Zones:
    [imd\_scotland\_iz.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_scotland_iz.csv)
-   Council Areas:
    [imd\_scotland\_lad.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_scotland_lad.csv)

### Northern Ireland

-   Super Output Areas:
    [imd\_northern\_ireland\_soa.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_northern_ireland_soa.csv)
-   Local Government Districts:
    [imd\_northern\_ireland\_lad.csv](https://github.com/matthewgthomas/IMD/raw/master/data-raw/imd_northern_ireland_lad.csv)

## Getting help

If you encounter a clear bug, please file an issue with a minimal
reproducible example on
[GitHub](https://github.com/matthewgthomas/IMD/issues).

------------------------------------------------------------------------

Please note that this project is released with a [Contributor Code of
Conduct](https://www.contributor-covenant.org/version/2/0/code_of_conduct/).
By participating in this project you agree to abide by its terms.
