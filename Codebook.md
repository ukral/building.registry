Codebook
================

# Introduction

This Codebook refers to the dataset “Building registry of Vienna in the
late 1920s”, briefly called digital building registry. The digital
building registry is the machine-readable version of [Häuser-Kataster
der Bundeshauptstadt Wien](https://permalink.obvsg.at/wbr/AC07637508).
The transformation from the analog to the digital version is documented
by a Data Descriptor, published in Nature Scientific Data.

# Dataset format

The dataset has a CSV format. The data records are separated by
semicolons (“;”). The decimal separator is a decimal point “.”. The
Universal Coded Character Set (UCS) is UTF-8.

# Dataset fields

The dataset includes 15 fields, as listed below. It includes fields from
the analog building registry, briefly called original data (OD) and
supplementary data (SD), which have been added to improve data
processing and validation as well as usability. It is noted that the
analog building registry consists of ten volumes, which have been
published between 1927 and 1930 (online table:
codebook\_analog.building.registry.csv). So, we attached a “.1920s” to
these database fields. The “.2010s” addition indicates that the
timestamp is in the late 2010s – between 2018 and 2019.

# Comments

This section comments on the individual data fields by giving background
information and details for using the data.

## ID

It is noted that the analog building registry has entries with multiple
building numbers per entry. These entries have been separated to have
only a single building number per data entry. The field “ID” is a
character that stands for a unique address. An address is the
combination of the street name and the building number. The next figure
exemplifies the address relation between the analog and the digital
building registry.

``` r
summary(cars)
```

    ##      speed           dist       
    ##  Min.   : 4.0   Min.   :  2.00  
    ##  1st Qu.:12.0   1st Qu.: 26.00  
    ##  Median :15.0   Median : 36.00  
    ##  Mean   :15.4   Mean   : 42.98  
    ##  3rd Qu.:19.0   3rd Qu.: 56.00  
    ##  Max.   :25.0   Max.   :120.00

## Including Plots

You can also embed plots, for example:

![](Codebook_files/figure-gfm/pressure-1.png)<!-- -->

Note that the `echo = FALSE` parameter was added to the code chunk to
prevent printing of the R code that generated the plot.
