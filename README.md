# building.registry
[![DOI](https://zenodo.org/badge/261487353.svg)](https://zenodo.org/badge/latestdoi/261487353)

The building schematic of Vienna in the late 1920s was a knowledge base for real estate and finance business. At this time, the schematic was published on paper. The  [Wienbibliothek im Rathaus](https://www.wienbibliothek.at/) scanned the documents and distribute the [Häuser-Kataster der Bundeshauptstadt Wien](https://permalink.obvsg.at/wbr/AC07637508) online in PDF format. We converted the PDFs into a machine-readable format.

The dataset includes 42,861 data entries (rows), which stand for buildings and properties, respectively. It includes 12 data fields (columns) as followed:

* Eight data fields originate from the [Häuser-Kataster der Bundeshauptstadt Wien](https://permalink.obvsg.at/wbr/AC07637508) with data records from the late 1920s: urban district number, street name, building number, position in a row of buildings, property area, number of floors, year of construction, year of purchase.
* Two data fields have been supplemented to facilitate geotagging. They include data records of the late 2010s: cadastral community number, street name.
* Two data fields have been supplemented to facilitate usability: identification number for each data entry, page number - which refers the the PDF page numbering of the [Häuser-Kataster der Bundeshauptstadt Wien](https://permalink.obvsg.at/wbr/AC07637508)


This repository includes the following key files.

* [Dataset](Dataset.csv): The CSV file includes the data records.
* [Codebook](./Codebook/Codebook.md), which specifies the dataset format, the data fields and comments the data fields.
* [R-Code for the Technical Validation](./Data.descriptor/Technical validation.Rmd) of the [Dataset](Dataset.csv)

This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/).
