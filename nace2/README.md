# Carbon footprint of NACE Rev. 2 codes

## Goal

### English

The goal of this dataset is to provide an estimate of the carbon monetary factors of a given NACE Rev. 2 code level 4. These monetary factors include scope 1, 2 and 3.

### French

L’objectif de ce jeu de données est de fournir un ratio monétaire, ou facteur monétaire d’intensité carbone, pour un code NACE Rév. 2 de niveau 4 donné. Ce ratio monétaire inclut les scopes 1, 2 et 3. Les codes APE ou NAF français sont équivalents à un niveau 5 dans la nomenclature NACE Rév. 2. Pour obtenir le ratio monétaire d’un code APE ou NAF français, il suffit donc de prendre le ratio monétaire associé aux quatre premiers caractères du code. Par exemple, le code NACE Rév. 2 de niveau 4 associé au code APE ou NAF 6419Z est 6419.

## Methodology

### Countries to EXIOBASE

Whenever a country of the ISO-3166-1 list existed in the EXIOBASE database, we mapped it automatically. Otherwise, we mapped the country of the ISO-3166 list either to:

1. A nearby country with a monetary factor that would likely be similar. For example, we mapped:

   - Andorra and Monaco to France
   - San Marino and Vatican to Italy
   - Gibraltar to Spain
   - Hong Kong and Macau to China

2. One of the rest of world regions based on the location of the country:

   - Central Asia and Pacific Asia Oceania Antarctica
   - East Europe and Iceland
   - Africa except Egypt and South Africa
   - Latin America except Brazil
   - Middle East Asia and Egypt.

### NACE Rev. 2 codes to EXIOBASE

NACE Rev. 2 codes were automatically mapped to EXIOBASE categories, using the [crosswalk table](https://ntnu.app.box.com/v/EXIOBASEconcordances/file/682195219009) provided by EXIOBASE.

## File description

The final output file is `results.csv`. We use commas as separators. Here is a quick description of each column:

| Column Name | Column Description |
| --- | --- |
| `NACE Code` | Code of the NACE Rev. 2 level 4 category. |
| `NACE Name` | Name of the NACE Rev. 2 level 4 category. |
| `EXIOBASE Code` | Code of the EXIOBASE category mapped to the NACE Rev. 2 code. |
| `EXIOBASE Name` | Name of the EXIOBASE category mapped to the NACE Rev. 2 code. |
| `Year` | Year of EXIOBASE data. |
| `Unit` | Unit of EXIOBASE monetary factor. |
| `AD` (example) | Monetary factor of a given MCC and a given country, represented by its ISO 3166-1 alpha-2 code. |


## Sources

### NACE Rev. 2 codes

This list of NACE Rev. 2 codes is provided by [Eurostat](https://ec.europa.eu/eurostat/web/products-manuals-and-guidelines/-/ks-ra-07-015). Only level 4 codes have been included in this dataset.

### EXIOBASE Monetary Factors

Monetary factors are extracted from [EXIOBASE3 monetary database](https://www.exiobase.eu/index.php/data-download/exiobase3hyb). This database is licensed under [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/). Any usage of EXIOBASE3 data should mention its licence. EXIOBASE3 includes monetary factors for 185 industries, across 49 geographical areas (44 countries and 5 rest of world areas), for all scopes (1, 2, 3). EXIOBASE3 source data range from 2011 to 2019.

### Countries

The list of countries has been extracted from the Github repository [ISO-3166-Countries-with-Regional-Codes](https://github.com/lukes/ISO-3166-Countries-with-Regional-Codes). This work is the result of merging data from two sources, the Wikipedia ISO 3166-1 article for alpha and numeric country codes, and the UN Statistics site for countries’ regional, and sub-regional codes. This database is licensed under [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Contributors

This work was performed by [Memo Bank](https://memo.bank/). Everyone is welcomed to contribute and improve this database. More information can be found in the [contributing guide](../CONTRIBUTING.md).
