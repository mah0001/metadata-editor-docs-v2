# Documenting indicators


## Data structure definition

The data structure definition (DSD) allows you to describe how the data are organized in the data file. This is the structural metadata for the indicator. The DSD in the Metadata Editor follows the SDMX standard.

In a data file, the indicator is supposed to be stored in long (not wide) format, i.e. in a database type of format where each row corresponds to one observation value. Each row must contain the core information required to define what the observation value represents, complemented by additional (optional) information.  

Typically, a data file for an indicator will look like one of the two options below, which use the population by sex of two countries as an example.

- ***Option 1***. In option 1, the population by sex is provided as three different indicators: male population, female population, and total population. The data file may look like this:

  ME_UG_v1-0-0_documenting_indicator_data_format_option1.png

 - ***Option 2***. In option 2, the information is provided as a single indicator ("population" with a *dimension* "sex" with values Male, Female, and Total.

  ME_UG_v1-0-0_documenting_indicator_data_format_option2.png

Organizations make their own decisions on how to organize their indicators. Using dimensions has the advantage of reducing the number of indicators. But it makes data discovery (indexing and search in data catalogs) somewhat more complex. In some cases, the use of dimensions is the only practical option. For example, data on population by age group (with 9 age groups + total), sex (2 options + total), and urban/rural (2 options with total) would require 10 x 3 x 3 = 90 different indicators. Maintaining a single indicator "population" with 3 dimensions would be more efficient (one indicator can have multiple dimensions).

Properly documenting the data structure of an indicator provides users (and machines) with the information they need to query and use the data.

A data structire definition consists of providing the following information about the indicator:
- ***Name:***
- ***Label:***
- ***Description:***
- ***Data type:***
  - ***String:***
  - ***Integer:***
  - ***Float:***
  - ***Date:***
  - ***Boolean:***
- ***Column type:***
  - ***Dimension:***
  - ***Time period:***
  - ***Measure:***
  - ***Attribute:***
  - ***Indicator ID:***
  - ***Indicator name:***
  - ***Annotation:***
  - ***Geography:***
  - ***Observation value:***
  - ***Periodicity:***
- ***Time period format:***
- ***Codelist:***
- ***Codelist reference:***
