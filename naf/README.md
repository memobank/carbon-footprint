# Carbon footprint of NAF codes

## Goal

### English

The goal of this dataset is to provide an estimate of the carbon footprint of a given NAF or APE code. NAF of APE codes are equivalent to NACE2 level 5 codes.

### French

L’objectif de ce jeu de données est de fournir un ratio monétaire, ou facteur monétaire d’intensité carbone, pour un code NAF ou APE donné. Les codes APE ou NAF sont équivalents à un niveau 5 dans la nomenclature NACE2.

## Methodology

### NAF to EXIOBASE

French NAF codes were automatically mapped to EXIOBASE categories, using [the NACE2 concordance table](https://ntnu.app.box.com/v/EXIOBASEconcordances/file/682195219009), based on their first four characters.

### NAF to ADEME

French NAF codes were manually mapped to ADEME categories whenever possible.

## File description

The final output file is `results.csv`. We use commas as separators. Here is a quick description of each column:

| Column Name        | Column Description                               |
| ------------------ | ------------------------------------------------ |
| `NAF Code`         | Code of the sector provided by INSEE.            |
| `NAF French Name`  | French name of the sector provided INSEE.        |
| `NAF English Name` | English name of the sector provided INSEE.       |
| `EXIOBASE Name`    | Name of EXIOBASE category mapped to a given NAF. |
| `ADEME Name`       | Name of ADEME category mapped to a given NAF.    |
| `Unit`             | Unit of monetary factor.                         |
| `EXIOBASE Factor`  | Monetary factor of a given NAF                   |
| `ADEME Factor`     | Monetary factor of a given NAF.                  |

## Sources

### NAF Codes

This list of NAF codes is provided by [INSEE](https://www.insee.fr/fr/information/2120875). Only level 5 codes have been included in this dataset.

### EXIOBASE Monetary Factors

Monetary factors for France are extracted from [EXIOBASE3 monetary database](https://www.exiobase.eu/index.php/data-download/exiobase3hyb). This database is licensed under [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/). Any usage of EXIOBASE3 data should mention its licence. EXIOBASE3 includes monetary factors for 185 industries, across 49 geographical areas (44 countries and 5 rest of world areas). Extraction from EXIOBASE was performed using [Climatiq.io](https://www.climatiq.io/explorer?source=EXIOBASE&year=2021) Data explorer. EXIOBASE3 source data range from 2011 to 2019.

### ADEME Monetary Factors

Monetary factors are provided by [ADEME](https://bilans-ges.ademe.fr/documentation/UPLOAD_DOC_EN/index.htm?ratio-monetaires.htm), a french public agency dedicated to the energy and management environment.

## Contributors

This work was performed by [Memo Bank](https://memo.bank/). Everyone is welcomed to contribute and improve this database. More information can be found in the [contributing guide](../CONTRIBUTING.md).
