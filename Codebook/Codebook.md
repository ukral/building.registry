Codebook
================

  - [Introduction](#introduction)
  - [Dataset format](#dataset-format)
  - [Dataset fields](#dataset-fields)
  - [Comments](#comments)
      - [ID](#id)
      - [UD.1920s](#ud.1920s)
      - [CC.2010s](#cc.2010s)
      - [STR.1920s](#str.1920s)
      - [STR.2010s](#str.2010s)
      - [BN.1920s](#bn.1920s)
      - [POS.1920s](#pos.1920s)
      - [AREA.1920s](#area.1920s)
      - [FLOORS.1920s](#floors.1920s)
      - [YoC.1920s](#yoc.1920s)
      - [YoP.1920s](#yop.1920s)
      - [Page.pdf](#page.pdf)
  - [Exemplary data records](#exemplary-data-records)

# Introduction

This Codebook refers to the dataset [Building schematic of Vienna in the
late 1920s](Dataset.csv), briefly called digital building schematic. The
dataset includes 42861 data entries (rows) and 12 data fields (columns).

# Dataset format

The dataset has a CSV format. The data records are separated by
semicolons (“;”). The decimal separator is a decimal point “.”. The
Universal Coded Character Set (UCS) is UTF-8.

# Dataset fields

The dataset includes 12 data fields. Eight data fields originate from
the analog building schematic, briefly called original data (OD) and
four data fields that have been supplemented (SD). The suffixes “.1920s”
and “.2010s” indicate data records in the late 1920s and late 2010s,
respectively.

| Field       | Name                  | Name.analog              | Description                                                                                     | Type |
| :---------- | :-------------------- | :----------------------- | :---------------------------------------------------------------------------------------------- | :--- |
| ID          | Identification number | \-                       | A unique number for each data entry.                                                            | SD   |
| UD.1920s    | Urban district        | \-                       | The number of the city district in the late 1920s.                                              | SD   |
| CC.2010s    | Cadastral community   | \-                       | The number of the cadastral community in in the late 2010s.                                     | SD   |
| STR.1920s   | Street name           | Gasse, Straße oder Platz | Name of alley, street, square in the late 1920s.                                                | OD   |
| STR.2010s   | Street name           | \-                       | Name of alley, street, square in the late 2010s.                                                | SD   |
| BN.1920s    | Building number       | Orientierungsnummer      | Street-based continuous numerating of buildings in the late 1920s.                              | OD   |
| POS.1920s   | Position              | Eck- oder Mittelhaus     | Position of the building, at the corner or in the middle of row of buildings in the late 1920s. | OD   |
| AREA.1920s  | Area                  | Ausmaß in m2             | Area of the property in m2 as recorded in the late 1920s.                                       | OD   |
| FLOORS.1920 | Floors                | Stockwerke               | Number of floors as recorded in the late 1920s.                                                 | OD   |
| YoC.1920s   | Year of construction  | Im Jahre erbaut          | Year of construction as recorded in the late 1920s.                                             | OD   |
| YoP.1920s   | Year of purchase      | Im Jahre erworben        | Year of purchase as recorded in the late 1920s.                                                 | OD   |
| Page.pdf    | Page number           | \-                       | The number of the PDF page in the respective volume of the analog building schematic.           | SD   |

# Comments

This section comments on the individual data fields by giving background
information and details for using the data.

## ID

It is noted that the analog building schematic has entries with multiple
building numbers per entry. These entries have been separated to have
only a single building number per data entry.

The field “ID” is a character that stands for a unique address. An
address is the combination of the street name and the building number.
The next figure exemplifies the address relation between the analog and
the digital building schematic. For instance, the address
“lerchenfelderstraße 100,102” is converted into the following data
entries:

| STR.1920s           | BN.1920s | ID       |
| :------------------ | -------: | :------- |
| lerchenfelderstraße |      100 | 11976\_0 |
| lerchenfelderstraße |      102 | 11976\_1 |

## UD.1920s

The field specifies the urban district in which the building is located
in the late 1920s. It is noted that the district boundaries differ from
those in the late 2010s. It is also stated that in the late 1920s the
city covered only the districts 1 to 21. The districts 22 and 23 were
amalgamated with the city after the 1920s.

## CC.2010s

The field specifies a numerical code of the cadastral community as given
in the late 2010s. It is noted that the geospatial data on
administrative boundaries of the city can be retrieved from the Austrian
[open government data
plattform](https://www.data.gv.at/katalog/dataset/verwaltungsgrenzen-vgd-stichtagsdaten-wien).

## STR.1920s

This field specifies the name of the street, alley or square as given in
the late 1920s.

## STR.2010s

This field specifies two type of entries.

| Entry                                          | Description                                                                                                                                                                                    |
| :--------------------------------------------- | :--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Respective name of the street, square or alley | This field specifies the name of the street, square or alley as given in the late 2010s. So, the dataset considers possible changes in the naming of streets and squares since the late 1920s. |
| Blank (“”)                                     | The name of the street, square or alley in the late 1920s does not exist in the late 2010s.                                                                                                    |

## BN.1920s

The field specifies the number of a building in a street as given in
late 1920s. An empty cell indicates no data record.

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

The field specifies the property area in m2. “NA” stands for “not
available”.

## FLOORS.1920s

The meaning of blank records is ambiguous and is considered to be
unknown unless additional efforts are undertaken to replace them by
evidence-based data from historical construction plans. The integer
floor numbers represent the floors above a ground floor and mezzanine
with a lower base floor, respectively. So, a building with a data record
“1” has two floors in total, one ground floor and one above.

| Entry | Total.floor.count |
| :---- | :---------------- |
| blank | unknown           |
| 1     | Two floors        |
| 2     | Three floors      |
| 3     | Four floors       |
| 4     | Five floors       |
| 5     | Six floors        |

## YoC.1920s

The field covers the year in which the building was constructed. Blank
entries stand for “not available”.

## YoP.1920s

The data field covers the year the building was transferred to the new
owner. Blank entries stand for “not available”.

## Page.pdf

The field includes integers that stand for the page number in the
scanned PDF version of the [analog building
schematic](permalink.obvsg.at/wbr/AC07637508).

# Exemplary data records

| ID | UD.1920s | CC.2010s | STR.1920s                | BN.1920s | STR.2010s                | POS.1920s | AREA.1920s | FLOORS.1920s | YoC.1920s | YoP.1920s | Page.pdf |
| :- | -------: | -------: | :----------------------- | :------- | :----------------------- | :-------- | ---------: | -----------: | :-------- | :-------- | -------: |
| 1  |        1 |     1004 | abrahamasanctaclaragasse |          | abrahamasanctaclaragasse |           |         NA |           NA |           |           |       15 |
| 2  |        1 |     1004 | adlergasse               | 4        |                          | M         |    1063.73 |            5 | 1878      | 1924      |       15 |
| 3  |        1 |     1004 | adlergasse               | 8        |                          | E         |     822.68 |            4 | 1892      | 1865      |       15 |
| 4  |        1 |     1004 | adlergasse               | 10       |                          | M         |     314.21 |            5 | 1892      | 1900      |       15 |
| 5  |        1 |     1004 | adlergasse               | 12       |                          | M         |     427.31 |            3 | 1911      | 1912      |       15 |
