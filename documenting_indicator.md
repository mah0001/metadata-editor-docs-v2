# Documenting indicators


## Data structure definition

The data structure definition (DSD) allows you to describe how the data are organized in the data file. This is the structural metadata for the indicator. The DSD in the Metadata Editor follows the SDMX standard.

In a data file, the indicator is supposed to be stored in long (not wide) format, i.e. in a database type of format where each row corresponds to one observation value. Each row must contain the core information required to define what the observation value represents, complemented by additional (optional) information.  

Typically, a data file for an indicator will look like one of the two options below, which use the population by sex of two countries as an example.

- ***Option 1***. In option 1, the population by sex is provided as three different indicators: Population, total", "Population, male", and "Population, female". The data file may look like this:

   ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_indicator_data_format_option1.png)

 - ***Option 2***. In option 2, the information is provided as a single indicator ("Population" with a *dimension* "sex" with values M, F or T for Male, Female, and Total).

   ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_indicator_data_format_option2.png)

Organizations make their own decisions on how to organize their indicators. Using dimensions has the advantage of reducing the number of indicators. But it makes data discovery (indexing and search in data catalogs) somewhat more complex. In some cases, the use of dimensions is the only practical option. For example, data on population by age group (with 9 age groups + total), sex (2 options + total), and urban/rural (2 options with total) would require 10 x 3 x 3 = 90 different indicators. Maintaining a single indicator "population" with 3 dimensions would be more efficient (one indicator can have multiple dimensions).

Properly documenting the data structure of an indicator provides users (and machines) with the information they need to query and use the data.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_indicator_data_structure_definition.png)

A data structure definition consists of providing the following information about the indicator and the way it is organized in the data file. This information will be provided **for each column of the data file**:
- ***Name:*** The column name
- ***Label:*** The column label
- ***Description:*** A brief description of the column
- ***Data type:*** The type of variable, with the following possible values: String, Integer, Float, Date, and Boolean.
- ***Column type:*** The type of column, with the following options:
  - ***Dimension:*** In our Option 2 example, column "sex" is a dimension.
  - ***Time period:*** The column indicates the time period to which the observation value applies. In our Option 2 example, "year" is a time period.
  - ***Measure:*** 
  - ***Attribute:*** 
  - ***Indicator ID:*** The column is the indicator unique identifier. Only one column can be an Indicator ID. In our Option 2 example, "IndicatorID" is the Indicator ID.
  - ***Indicator name:*** The column is the name (or title) of the indicator. In our Option 2 example, "Name" is the Indicator ID.
  - ***Annotation:*** 
  - ***Geography:*** The geographic area to which the value corresponds. In our example, column "country" is the geography.
  - ***Observation value:*** The observation value (the "data" itself). In our example, column "value" is the observation value.
  - ***Periodicity:*** 
- ***Time period format:*** Time period format is used to indicate the format of the date in the column identified as Time period. In our Option 2 example, Time period format is "YYYY" as we have data by year.
- ***Codelist:***
- ***Codelist reference:***
