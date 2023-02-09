# Carbon footprint of payment cards

## Goal

### English

The goal of this dataset is to provide an estimate of the carbon footprint of purchases made by payment cards through the Visa or Mastercard network. The estimate is based on the Merchant Category Code of the transaction, the country of the merchant, and monetary factors.

### French

L’objectif de ce jeu de données est de fournir une estimation de l’empreinte carbone d’un achat réalisé par carte bancaire via le réseau Visa ou Mastercard. Cette estimation est calculée à partir de la catégorie du marchand, de son pays, et d’un facteur monétaire.

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

### Merchant Category Code to EXIOBASE

Mapping between the list of Merchant Category Codes and EXIOBASE was done manually and may be subject to subjective opinions. EXIOBASE segments its data across 185 categories but only 34 of them were used as part of this mapping. Please note that this mapping is not official and reflects only the point of views of contributors.

## File description

The final output file is `results.csv`. We use commas as separators. Here is a quick description of each column:

| Column Name | Column Description |
| --- | --- |
| `MCC` | Merchant Category Code number provided by Visa. |
| `MCC Name` | Name of Merchant Category Code provided by Visa. |
| `EXIOBASE Name` | Name of EXIOBASE category mapped to a given MCC. |
| `Network` | Payment network using this MCC: Visa and/or Mastercard. |
| `Year` | Year of EXIOBASE data. |
| `Unit` | Unit of EXIOBASE monetary factor. |
| `AD` (example) | Monetary factor of a given MCC and a given country, represented by its ISO 3166-1 alpha-2 code. |

## Sources

### Merchant Category Codes (MCC)

This list of MCCs combines MCC from both Visa and Mastercard network:

- The list of Visa MCC was released publicly in [November 2021](https://usa.visa.com/content/dam/VCOM/download/merchants/visa-merchant-data-standards-manual.pdf);
- The list of Mastercard MCC was released publicly in [October 2022](https://www.mastercard.us/content/dam/public/mastercardcom/na/global-site/documents/quick-reference-booklet-merchant.pdf).

Both sources are used officially by institutions like [Citibank](https://www.citibank.com/tts/solutions/commercial-cards/assets/docs/govt/Merchant-Category-Codes.pdf) and [Wikipedia](https://en.wikipedia.org/wiki/Merchant_category_code). More up-to-date versions may exist but have not been provided by Visa or Mastercard so far.

### EXIOBASE Monetary Factors

Monetary factors are extracted from [EXIOBASE3 monetary database](https://www.exiobase.eu/index.php/data-download/exiobase3hyb). This database is licensed under [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/). Any usage of EXIOBASE3 data should mention its licence. EXIOBASE3 includes monetary factors for 185 industries, across 49 geographical areas (44 countries and 5 rest of world areas). Extraction from EXIOBASE was performed using [Climatiq.io](https://www.climatiq.io/explorer?source=EXIOBASE&year=2021) Data explorer. EXIOBASE3 source data range from 2011 to 2019.

### Countries

The list of countries has been extracted from the Github repository [ISO-3166-Countries-with-Regional-Codes](https://github.com/lukes/ISO-3166-Countries-with-Regional-Codes). This work is the result of merging data from two sources, the Wikipedia ISO 3166-1 article for alpha and numeric country codes, and the UN Statistics site for countries’ regional, and sub-regional codes. This database is licensed under [Creative Commons Attribution-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-sa/4.0/).

## Additional resources

To understand how we use this data on our own service, you can find more information on its [help centre](https://aide.memo.bank/article/356-comprendre-lien-paiement-carte-emissions-co2) (in French).

## Contributors

This work was performed by [Memo Bank](https://memo.bank/), an independent bank for small and medium businesses and reviewed by [Magelan](https://www.magelan.tech/), a consulting firm specialised in transitioning to a low-carbon economy. Everyone is welcomed to contribute and improve this database. More information can be found in the [contributing guide](../CONTRIBUTING.md).
