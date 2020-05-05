Codebook
================

  - [Introduction](#introduction)
  - [Dataset format](#dataset-format)
  - [Dataset fields](#dataset-fields)
  - [Comments](#comments)
      - [ID](#id)
      - [UD.1920s](#ud.1920s)
      - [UD.2010s](#ud.2010s)
      - [STR.1920s](#str.1920s)
      - [STR.2010s](#str.2010s)
      - [BN.1920s](#bn.1920s)
      - [ADR.1920s](#adr.1920s)
      - [ADR.2010s](#adr.2010s)
      - [POS.1920s](#pos.1920s)
      - [AREA.1920s](#area.1920s)
      - [FLOORS.1920s](#floors.1920s)
      - [YoC.1920s](#yoc.1920s)
      - [YoP.1920s](#yop.1920s)
      - [Page.orig](#page.orig)
      - [Page.pdf](#page.pdf)
  - [Exemplary data records](#exemplary-data-records)

# Introduction

This Codebook refers to the dataset [Building registry of Vienna in the
late 1920s](Dataset.csv), briefly called digital building registry.

# Dataset format

The dataset has a CSV format. The data records are separated by
semicolons (“;”). The decimal separator is a decimal point “.”. The
Universal Coded Character Set (UCS) is UTF-8.

# Dataset fields

The dataset includes 15 fields, as listed below. It includes fields from
the analog building registry, briefly called original data (OD) and
supplementary data (SD), which have been added to improve data
processing and validation as well as usability. It is noted that the
analog building registry consists of [ten
volumes](Codebook_files/table_volumes.analog.building.registry.csv),
which have been published between 1927 and 1930. So, we attached a
“.1920s” to dataset fields that originate from the analog building
registry. The “.2010s” addition indicate that the timestamp is in the
late 2010s – between 2018 and 2019.

| Field       | Name                  | Name.analog              | Description                                                                                                                                    | Type |
| :---------- | :-------------------- | :----------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------- | :--- |
| ID          | Identification number | \-                       | A unique number for each data entry.                                                                                                           | SD   |
| UD.1920s    | Urban district        | \-                       | The number of the city district in the late 1920s.                                                                                             | SD   |
| UD.2010s    | Urban district        | \-                       | The number of the city district in in the late 2010s.                                                                                          | SD   |
| STR.1920s   | Street name           | Gasse, Straße oder Platz | Name of alley, street, square in the late 1920s.                                                                                               | OD   |
| STR.2010s   | Street name           | \-                       | Name of alley, street, square in the late 2010s.                                                                                               | SD   |
| BN.1920s    | Building number       | Orientierungsnummer      | Street-based continuous numerating of buildings in the late 1920s.                                                                             | OD   |
| ADR.1920s   | Address               | \-                       | Street name and building number in the late 1920s.                                                                                             | OD   |
| ADR.2010s   | Address               | \-                       | Address in the late 2010s if street name or building number have changed, otherwise identical with ADR.1920s                                   | SD   |
| POS.1920s   | Position              | Eck- oder Mittelhaus     | Position of the building, at the corner or in the middle of row of buildings in the late 1920s.                                                | OD   |
| AREA.1920s  | Area                  | Ausmaß in m2             | Area of the property in m2 as recorded in the late 1920s.                                                                                      | OD   |
| FLOORS.1920 | Floors                | Stockwerke               | Number of floors as recorded in the late 1920s.                                                                                                | OD   |
| YoC.1920s   | Year of construction  | Im Jahre erbaut          | Year of construction as recorded in the late 1920s.                                                                                            | OD   |
| YoP.1920s   | Year of purchase      | Im Jahre erworben        | Year of purchase as recorded in the late 1920s.                                                                                                | OD   |
| Page.orig   | Page number           | \-                       | The page number as given at the top of each page in the analog building registry. It is noted that pages without addresses lack a page number. | SD   |
| Page.pdf    | Page number           | \-                       | The number of the PDF page in the respective volume.                                                                                           | SD   |

# Comments

This section comments on the individual data fields by giving background
information and details for using the data.

## ID

It is noted that the analog building registry has entries with multiple
building numbers per entry. These entries have been separated to have
only a single building number per data entry.

The field “ID” is a character that stands for a unique address. An
address is the combination of the street name and the building number.
The next figure exemplifies the address relation between the analog and
the digital building registry. For instance, the address
“lerchenfelderstraße 100,102” is converted into the following data
entries:

| STR.1920s           | BN.1920s | ID       |
| :------------------ | -------: | :------- |
| lerchenfelderstraße |      100 | 10063\_0 |
| lerchenfelderstraße |      102 | 10063\_1 |

## UD.1920s

The field specifies the urban district in which the building is located
in the late 1920s. It is noted that the district boundaries differ from
those in the late 2010s. It is also stated that in the late 1920s the
city covered only the districts 1 to 21. The districts 22 and 23 were
amalgamated with the city after the 1920s.

## UD.2010s

The field specifies the number of the urban district as given in the
late 2010s. It is noted that the geospatial data on administrative
boundaries of the city and the districts can be retrieved
[online](https://www.data.gv.at/katalog/dataset/1a22d558-544a-46c1-95b9-baa77d2bb485).

## STR.1920s

This field specifies the name of the street / square as given in the
late 1920s.

## STR.2010s

This field species two type of entries.

| Entry                                          | Description                                                                                                                                                                          |
| :--------------------------------------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Respective name of the street / square / alley | This field specifies the name of the street / square / alley as given in the late 2010s. So, it respects possible changes in the naming of streets and squares since the late 1920s. |
| Blank (“”)                                     | The name of the street / square / alley in the late 1920s does not exist in the late 2010s.                                                                                          |

## BN.1920s

The field specifies the number of a building in a street as given in
1928. An empty cell indicates no data record.

## ADR.1920s

This field defines the address in the late 1920s.

| Entry              | Description                                             |
| :----------------- | :------------------------------------------------------ |
| Respective address | This field combines the “STR.1920s” and the “BN.1920s”. |
| Blank (“”)         | The data entry indicates a lack of “BN.1920s”.          |

## ADR.2010s

This field combines the “STR.2010S” and the “BN.1920s”.

| Entry              | Description                                                                                                                                                                                                                                                              |
| :----------------- | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Respective address | The address corresponds to ADR.1920s and has been verified by the address register of 2018. It is noted that the street name between ADR.2010S and ADR.1920S might be not identical because street name might have changed between the late 1920s and late 2010s.        |
| Blank (“”)         | This indicates that the ADR.1920s could not be verified by an entry in the address register of the late 2010s. Geotagging the ADR.1920s needs to be done manually by screening historical literature. It is noted that addresses without “BN.1920s” are also left blank. |

## POS.1920s

The field specifies the position of the building within a row of
buildings.

| Entry          | Description                                                            |
| :------------- | :--------------------------------------------------------------------- |
| E              | The string “E” stands for a corner building (in German: Eckhaus)       |
| M              | “M” stands for the middle in the building row (in German: Mittelhaus). |
| „M,E“ or „E,M“ | Indicates two buildings at the same address                            |
| Blank (“”)     | No information available                                               |

## AREA.1920s

The field lacks comments in the analog building registry \[2\]. We found
evidence that the field area stands for the property area in m2 and not
for the footprint of the buildings. “NA” stands for “not available”.

## FLOORS.1920s

The field includes integers from “1” to “5”. We found evidence that “1”
stands for ground floor (British English) or first floor (American
English) plus an additional floor. Following this logic, buildings with
just a ground floor have not been recorded in the analog building
registry.

| Entry | Interpretation           |
| ----: | :----------------------- |
|    NA | No information available |
|     1 | Two floors               |
|     2 | Three floors             |
|     3 | Four floors              |
|     4 | Five floors              |
|     5 | Six floors               |

## YoC.1920s

The field covers the year in which the building was constructed. Blank
entries stand for “not available”.

## YoP.1920s

The data field covers the year the building was transferred to the new
owner. Blank entries stand for “not available”.

## Page.orig

The page number as given on top of each page in the analog building
registry. “NA” stands for “not available”.

## Page.pdf

The field includes integers that stand for the page number in the
scanned PDF version in the respective volume. It facilitates
cross-referencing between the analog and the machine-readable version of
the building registry. “NA” stands for “not available”.

# Exemplary data records

| ID  | UD.1920s | UD.2010s | STR.1920s                | STR.2010s                | BN.1920s | ADR.1920s     | ADR.2010s | POS.1920s | AREA.1920s | FLOORS.1920s | YoC.1920s | YoP.1920s | Page.orig | Page.pdf |
| :-- | -------: | -------: | :----------------------- | :----------------------- | :------- | :------------ | :-------- | :-------- | ---------: | -----------: | :-------- | :-------- | --------: | -------: |
| 1\_ |        1 |        1 | abrahamasanctaclaragasse | abrahamasanctaclaragasse |          |               |           |           |         NA |           NA |           |           |        NA |       NA |
| 2\_ |        1 |        1 | adlergasse               |                          | 4        | adlergasse 4  |           | M         |    1063.73 |            5 | 1878      | 1924      |        11 |       15 |
| 3\_ |        1 |        1 | adlergasse               |                          | 8        | adlergasse 8  |           | E         |     822.68 |            4 | 1892      | 1865      |        11 |       15 |
| 4\_ |        1 |        1 | adlergasse               |                          | 10       | adlergasse 10 |           | M         |     314.21 |            5 | 1892      | 1900      |        11 |       15 |
| 5\_ |        1 |        1 | adlergasse               |                          | 12       | adlergasse 12 |           | M         |     427.31 |            3 | 1911      | 1912      |        11 |       15 |
