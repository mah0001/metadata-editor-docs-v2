# Documenting geographic datasets and services

## The ISO 19100 metadata standards 

To make geographic information discoverable and to facilitate their dissemination and use, the ISO Technical Committee on Geographic Information/Geomatics (ISO/TC211) created a set of metadata standards to describe geographic **datasets** (ISO 19115), geographic **data structures** (ISO 19115-2 / ISO 19110), and geographic **data services** (ISO 19119). These standards have been "unified" into a common XML specification (ISO 19139). This set of standards, known as the ISO 19100 series, served as the cornerstone of multiple initiatives to improve the documentation and management of geographic information such as the [Open Geospatial Consortium (OGC)](https://www.ogc.org/), the [US Federal Geographic Data Committee (FDGC)](https://www.fgdc.gov/), the [European INSPIRE directive](https://inspire.ec.europa.eu), or more recently the [Research Data Alliance (RDA)](https://rd-alliance.org/), among others.

The ISO 19100 standards have been designed to cover the large scope of geographic information. The level of detail they provide goes beyond the needs of most data curators. What we use in the Metadata Editor is a subset of the standards, which focuses on what we consider as the most relevant metadata elements to describe and catalog geographic datasets and services. 
                                                  
Geographic information metadata standards cover three types of resources: (i) datasets (which can be of vector or raster type), (ii) data structure definitions, and (iii) data services. Each one of these three components is the object of a specific standard. To support their implementation, a common XML specification (ISO 19139) covering the three standards has been developed. The geographic metadata standard is however a very complex standard. Its use requires expertise not only in data documentation, but also in the use of geospatial data. We provide in this chapter some information that readers who are not familiar with geographic data may find useful to better understand the purpose and use of the geographic metadata standards.

## Documenting geographic datasets, series, and services

**GEOGRAPHIC DATASETS**

**Geographic datasets** Geographic datasets refers to the actual stored data about the Earth’s features, phenomena, or events. Geographic datasets "identify and depict geographic locations, boundaries and characteristics of features on the surface of the earth. Geographic datasets can be vector data (points, lines, polygons) or raster data (grids, pixels, imagery). They include geographic coordinates (e.g., latitude and longitude) and data associated to geographic locations (...)". (Source: https://www.fws.gov/gis/) The ISO 19115 standard defines the structure and content of the metadata to be used to document geographic datasets. The ISO 19115 standard is split into two parts covering:
- ***vector data*** (ISO 19115-1), and 
- ***raster data*** including imagery and gridded data (ISO 19115-2). 
The elements of ISO 19115 are included in the XML specification ISO 19139.

*Vector* and *raster* spatial datasets are built with different structures and formats. The following summarizes how these two categories differ and how they can be processed using the R software. The descriptions of vector and raster data provided in this chapter are adapted from:
   - https://gisgeography.com/spatial-data-types-vector-raster/
   - https://datacarpentry.org/organization-geospatial/02-intro-vector-data/index.html]

**GEOGRAPHIC DATASETS SERIES**

**Geographic datasets series** Geographic datasets can be organized in ***series***. In ISO 19139 (and ISO 19115), *series* refers to a collection of related datasets that are grouped together because they share a common purpose, theme, method of production, or spatial/temporal extent. In other words, a series is a set of datasets that are logically connected and can be described together at a higher level.

Examples:
- A series of annual land use maps for different years (2000, 2005, 2010, etc.).
- A collection of satellite images covering different tiles of a country.
- A set of topographic maps produced at the same scale for different regions.

In the metadata, some elements in the ISO 19139 are dedicated to provide information on series. You can describe the series itself at a general level. Then you can have metadata for individual datasets linked to that series. This helps avoid duplication — common information is stored once at the series level, and dataset-level metadata can focus on the differences. In ISO 19139 XML, you will often see fields like:
- resourceScope set to series (to show you are describing a series, not a single dataset);
- aggregationInfo to link datasets to their series or services.

**GEOGRAPHIC DATA SERVICES**

**Geographic data services** refers to  operations or set of operations that allows users to access, manipulate, transform, analyze, or visualize geographic data over a network or system. It’s not the data itself — it’s the functionality provided to interact with the data. In other words, a geographic data service is something you can call or use to work with geographic data without downloading the full dataset first. Geographic data servies are documented using metadata elements from the ISO 19119 metadata standard. The elements of ISO 19119 are included in the XML specification ISO 19139.


### Vector data 

Vector data are comprised of **points**, **lines**, and **polygons** (areas). 

A vector **point** is defined by a single x, y coordinate. Generally, vector points are a latitude and longitude with a spatial reference frame. A point can for example represent the location of a building or facility. When multiple dots are connected in a set order, they become a vector **line** with each dot representing a **vertex**. Lines usually represent features that are linear in nature, like roads and rivers. Each bend in the line represents a vertex that has a defined x, y location. When a set of 3 or more vertices is joined in a particular order and closed (i.e. the first and last coordinate pairs are the same), it becomes a **polygon**. Polygons are used to show boundaries. They will typically represent lakes, oceans, countries and their administrative subdivisions (provinces, states, districts), building footprints, or outline of survey plots. Polygons have an area (which will correspond to the square-footage for a building footprint, to the acreage for an agricultural plot, etc.) 

Vector data are often provided in one of the following file formats:

   - ESRI Shapefile (actually a zip set of files; not standard and limited as it is based on an outdated DBF format, but still widely used);
   - ESRI GeoDatabase file (not a standard format, but widely used);
   - GML: the Official OGC geospatial standard format, used by standard spatial data services;
   - GeoPackage: the OGC recommended standard for handling vector data;
   - GeoJSON: another OGC standard, often used when a *service* is associated to the data;
   - KML/KMZ: [Keyhole Markup Language](https://en.wikipedia.org/wiki/Keyhole_Markup_Language), an XML notation for expressing geographic annotation and visualization within two-dimensional maps and three-dimensional Earth browsers;
   - CSV file: Comma-separated values files, with geometries provided in OGC Well-Known-Text (WKT);
   - OSM: An XML-formatted file containing "nodes" (points), "ways" (connections), and "relations" from [OpenStreetMap](https://www.openstreetmap.org) format. 

**EXAMPLE**

The figure below provides an example of vector data extracted from [Open Street Map](https://www.openstreetmap.org/node/1376501203#map=18/27.47008/89.63725) for a part of the city of Thimphu, Bhutan (as of 17 May, 2021). 

![image](img/ME_UG_v1-0-0_documenting_geographic_vector_OSM.png)


### Raster data

**Raster data** are made up of pixels, also referred to as *grid cells*. Satellite imagery and other remote sensing data are raster datasets. Grid cells in raster data are usually (but not necessarily) regularly-spaced and square. Data stored in a raster format is arranged in a grid without storing the coordinates of each cell (pixel). The coordinates of the corner points and the spacing of the grid can be used to calculate (rather than to store) the coordinates of each location in a grid.

Any given pixel in a grid stores one or more values (in one or more bands). For example, each cell (pixel) value in a satellite image has a red, a green, and a blue value. Cells in raster data could represent anything from elevation, temperature, rainfall, land cover, population density, or others. (Source: https://worldbank.github.io/OpenNightLights/tutorials/mod2_1_data_overview.html) 

Raster data can be **discrete** or **continuous**. Discrete rasters have distinct themes or categories. For example, one grid cell can represent a land cover class, or a soil type. In a discrete raster, each thematic class can be discretely defined (usually represented by an integer) and distinguished from other classes. In other words, each cell is definable and its value applies to the entire area of the cell. For example, the value 1 for a class might indicate "urban area", value 2 "forest", and value 3 "others". Continuous (or non-discrete) rasters are grid cells with gradual changing values, which could for example represent elevation, temperature, or an aerial photograph.

The difference between vector and raster data, and between different types of vectors, is clearly illustrated in the figure below taken from the World Bank's [Light Every Night GitHub repository](https://worldbank.github.io/OpenNightLights/tutorials/mod2_1_data_overview.html).

![image](img/ME_UG_v1-0-0_documenting_geographic_vector_raster.png)

Raster data are sometimes converted into vector data. For example, a building footprint layer (vector data, composed of polygons) can be derived from a satellite image (raster data). Such conversions can be implemented in a largely automated manner using machine learning algorithms. 

![image](img/ME_UG_v1-0-0_documenting_geographic_image_to_vector.png)

Source: https://blogs.bing.com/maps/2019-09/microsoft-releases-18M-building-footprints-in-uganda-and-tanzania-to-enable-ai-assisted-mapping

Raster data are often provided in one of the following file formats:

   - GeoTiFF (standard): Most of the remote sensing data are stored as GeoTIFF files. https://www.ogc.org/standards/geotiff
   - NetCDF (standard) https://www.unidata.ucar.edu/software/netcdf/docs/netcdf_introduction.html
   - ECW: https://en.wikipedia.org/wiki/ECW_(file_format)
   - JPEG 2000: https://fr.wikipedia.org/wiki/JPEG_2000
   - MrSid: https://en.wikipedia.org/wiki/MrSID
   - ArcGrid (ESRI Grid format)

**GeoTIFF** is a popular file format for raster data. A *Tagged Image File Format* (TIFF or TIF) is a file format designed to store raster-type data. A GeoTIFF file is a TIFF file that contains specific tags to store structured geospatial metadata including:

   - Spatial extent: the area coverage of the file
   - Coordinate reference system: the projection / coordinate reference system used
   - Resolution: the spatial extent of each pixel (spatial resolution)
   - Number of layers: number of layers or bands available in the file

TIFF files can be read using (among other options) the R package [*raster*](https://cran.r-project.org/package=raster) or the Python library [*rasterio*](https://pypi.org/project/rasterio/). 

GeoTIFF files can also be provided as **Cloud Optimized GeoTIFFS (COGs)**. In COGs, the data are structured in a way that allows them to be shared via web services which allow users to query, visualize, or download a user-defined subset of the content of the file, without having to download the entire file. This option can be a major advantage, as geoTIFF files generated by remote sensing/satellite imagery can be very large. Extracting only the relevant part of a file can save significant time and storage space.

**EXAMPLE**

The example below shows the spatial distribution of the Ethiopian population in 2020. The data file was downloaded from the [WorldPop](https://www.worldpop.org/) website on 17 May 2021.

![image](img/ME_UG_v1-0-0_documenting_geographic_worldpop_ethiopia.png)


### Combining vector and raster data in GIS applications

In GIS applications, vector and raster data are often combined into multi-layer datasets, as shown in the figure below extracted from the [County of San Bernardino (US) website](http://sbcounty.gov/). 

![image](img/ME_UG_v1-0-0_documenting_geographic_GIS_layers.png)


## Describing data structures - The ISO 19115-2 and ISO 19110 standards

The ISO 19115-2 provides the necessary metadata elements to describe the structure of raster data. The ISO 19115-1 standard does not provide all necessary metadata elements needed to describe the structure of vector datasets. The description of data structures for vector data (also referred to as *feature types*) is therefore often omitted. The ISO 19110 standard solves that issue, by providing the means to document the structure of vector datasets (column names and definitions, codes and value labels, measurement units, etc.), which will contribute to making the data more discoverable and usable.


## Unified metadata specification - The ISO/TS 19139 standard

The three metadata standards previously described - ISO 19115 for vector and raster datasets, ISO 19110 for vector data structures, and ISO 19119 for data services, provide a set of concepts and definitions useful to describe the geographic information. To facilitate their practical implementation, a digital specification, which defines how this information is stored and organized in an electronic metadata file, is required. The ISO/TS 19139 standard, an XML specification of the ISO 19115/10110/19119/, was created for that purpose.

The ISO/TS 19139 is a standard used worldwide to describe geographic information. It is the backbone for the implementation of [INSPIRE](https://inspire.ec.europa.eu/) dataset and service metadata in the European Union. It is supported by a wide range of tools, including desktop applications like [Quantum GIS](https://qgis.org/en/site/), [ESRI ArcGIS](https://www.arcgis.com/index.html)), and OGC-compliant metadata catalogs (e.g., [GeoNetwork](https://geonetwork-opensource.org/)) and geographic servers (e.g., [GeoServer](http://geoserver.org/)). 

ISO 19139-compliant metadata can be generated and edited using specialized metadata editors such as [CatMDEdit](http://catmdedit.sourceforge.net/) or [QSphere](https://www.fgdc.gov/organization/working-groups-subcommittees/mwg/iso-metadata-editors-registry/qsphere), or using programmatic tools like Java Apache SIS or the R packages [geometa](https://cran.r-project.org/web/packages/geometa/index.html) and [geoflow](https://github.com/eblondel/geoflow), among others.

The Metadata Editor uses the ISO 19139 to provide a solution compatible with the ISO 19115, ISO 19110, and ISO 19119 standards.


## Metadata templates or profiles for the practical implementation of ISO 19139

The ISO 19139 specification is complex. To enable and simplify its use in the Metadata Editor, we produced a JSON version of (part of) the standard. We selected the elements we considered most relevant for our purpose, and organized them into the JSON schema described below. For data curators with limited expertise in XML and geographic data documentation, this JSON schema will make the production of metadata compliant with the ISO 19139 standard easier. 

Some organizations have sought to make the use of ISO 19139 manageable, by defining *templates* or *profiles* that consist of subsets. This includes the INSPIRE set of elements defined by the European Union, and the GEMINI set of elements defined by the United Kingdom.

The Metadata Editor is also provided with recommended templates that only contain the elements of the ISO 19139 that are considered the most useful for the documentation of geographic datasets and services. The template provided in the Metadata Editor contains all elements from the INSPIRE and GEMINI profiles, and a few more.


### INSPIRE - Infrastructure for Spatial Information in Europe

The INSPIRE geographic metadata template refers to a standardized set of metadata elements that organizations in Europe must use to describe geographic datasets and services under the INSPIRE Directive. It aims to create a European-wide, interoperable spatial data infrastructure to support environmental policies and activities that impact the environment.

The INSPIRE metadata template is based mainly on ISO 19115 (for datasets) and ISO 19119 (for services), but it specifies exactly which metadata elements are mandatory, conditional, or optional for INSPIRE compliance. It also sometimes restricts choices or defines controlled vocabularies (for example, for topics, keywords, spatial scope) to ensure harmonization across countries. The rules are detailed in the INSPIRE Metadata Regulation (Commission Regulation (EC) No 1205/2008) and its technical guidelines.

See the INSPIRE knowledge base at https://knowledge-base.inspire.ec.europa.eu/index_en


### UK GEMINI 2.3

GEMINI is the UK standard for spatial metadata. It's based on ISO 19139 and takes into account the needs of INSPIRE too. 

See:
- https://guidance.data.gov.uk/publish_and_manage_data/harvest_or_add_data/harvest_data/gemini/#gemini-and-iso-19139-metadata
- A description of UK GEMINI 2.3 2020-04-07 dataset or series: [https://agiorguk.github.io/gemini/1062-gemini-datasets-and-data-series.html](https://agiorguk.github.io/gemini/1037-uk-gemini-introduction.html)
  
  
## Documenting a geographic dataset 

This section describes how to document a geographic dataset (vector or raster) using the Metadata Editor. Documenting a data service follows the exact same principles, except that the option to extract metadata from data files does not apply when documenting a data service.

The metadata template provided with the Metadata Editor identifies metadata elements that are specific to vector or raster datasets, or to data services.


### Prepare your materials

Before you start documenting a geographic dataset, collect and organize the dataset and the related materials (documentation, logo, others) in a folder (and subfolders as useful). No structure is imposed. The objective is to ensure that materials are not scattered across folders and drives.

If you plan to provide one or multiple previews of the datasets, generate these previews and save them as image files (e.g., JPEG).


### Create a project

The first step in documenting a dataset is to create a new project. You do that by clicking on `CREATE NEW PROJECT` in the *My projects* page. Select *Geospatial* as data type. This will open a new, untitled project *Home* page. 

In the **Templates** frame, select the template you want to use to document the dataset. A default template is proposed; no action is needed if you want to use that template. Otherwise, switch to another template by clicking on the template name. Note that you can at any time change the template used for the documentation of a project. The selected template will determine what you see in the navigation tree and in the metadata entry pages. 

> Switching from one template to another will not impact the metadata that has already been entered; no information will be deleted from the metadata.

Once a project has been created, you can import the data files (if available) and start documenting the dataset. 


### Extract metadata from data files [under development - to be available in version 1.1 of the application]

The Metadata Editor allows you to extract metadata contained in geographic datasets. The following formats are supported:
- Vector datasets: GeoJSON, Shapefile (SHP), KML, GPKG, GDB
- Raster datasets: NetCDF (NC), geoTIF, BIL, ASCII (XYZ), GeoPDF (PDF), JPG, GIF, ADF, OVR

To extract information from data files:
- Click on DATA in the navigation bar. The data import page will be displayed. Select the data file(s) to be imported, then click `IMPORT`.  

The metadata that will be extracted will be automatically entered in the relevant metadata elements. What can be extracted depends on the data format, and on what the data producer may have included in the data files. Typically, the following metadata will be extracted: Filename, Bounding boxes, Reference system, Features (for vector datasets), Bands, and more.


### Enter additional metadata

We describe below the metadata elements included in the recommended INSPIRE + GEMINI + ADDITIONAL ELEMENTS template. This is only a subset of the elements contained in the ISO 19139. If you developed or imported a different, more comprehensive template, consult the description of metadata elements provided by the ISO 19139 documentation.

**DOCUMENT DESCRIPTION**

This section is not specific to geographic datasets. It corresponds to the *Document description* section of the DDI Codebook metadata standard (for microdata) and to the *Information on metadata* section in other metadata standards and schemas. This section contains metadata on the metadata, structured in a format consistent across metadata standards supported by the Metadata Editor. The content of this section is maintly intended to be used by catalog administrators, and will not be exported to ISO 19139 metadata files. 

**DESCRIPTION**

**METADATA**

- **`Hierarchy level`** This is the type of resource being described by the metadata and it is filled in with a value from a classification of the resource based on its scope. The choice of Resource Type will be probably the first decision made by the user and it will define the metadata elements that should be filled.

  The hierarchy level defines the scope of the resource. It indicates whether the resource is a collection, a dataset, a series, a service, or another type of resource. The ISO 19139 provides a controlled vocabulary for this element. It is recommended but not mandatory to make use of it. The most relevant levels for the purpose of cataloguing geographic data and services are **dataset** (for raster and vector datasets), **series** (collections of related da)tasets that share a common purpose, and **service**.

- **`Primary ID`** The "Primary ID" (also referred to as IDNO) is a unique identification number used to identify the study (geographic dataset or service). A unique identifier is required for cataloguing purpose, so this element is declared as "Required". The identifier will allow users to cite the study properly. The identifier must be unique within the catalog. Ideally, it should also be globally unique; the recommended option is to obtain a Digital Object Identifier (DOI) for the study. Alternatively, the "Primary ID" can be constructed by an organization using a consistent scheme. The identifier should not contain blank spaces.

- **`Parent identifier`** (*for hierarchy level = series, not for datasets*) A geographic data resource can be a subset of a larger dataset. For example, an aquatic species distribution map can be part of a data collection covering all species, or the 2010 population census dataset of a country can be part of a dataset that includes all population censuses for that country since 1900. In such case, the parent identifier metadata element can be used to identify this higher-level resource. As for the fileIdentifier, the parentIdentifier must be a unique identifier persistent in time. In a data catalog, a parentIdentifier will allow the user to move from one dataset to another. The parentIdentifier is generally applied to datasets, although it may in some cases be used in data services descriptions.

- **`Metadata date`** Date and time when the metadata record was created or updated. Requires an extended ISO 8601 formatted combined UTC date and time string (2009-11-17T10:00:00).
  
- **`Metadata language`** Main language used in the metadata description. It is recommended to select a value from a controlled vocabulary, for example that provided by ISO 639-2.

- **`Metadata contact`** 
  - **`Individual name`** The responsible party (person) in charge of the feature catalogue production.
  - **`Organisation name`** The responsible party (organization) in charge of the feature catalogue production.
  - **`Email`** 
  - **`Phone`**  
  - **`Address`** 
      - **`Delivery point`** Physical address - Street, building number, etc.
      - **`City`** Physical address - City name
      - **`Postal code`** Physical address - Postal code
      - **`Country`** Physical address - Country name
    - **`Online resource`** 
      - **`Name`** Name of the online resource. In case of a geographic standard data services, this should be filled with the identifier of the resource as published in the service. Example, for an OGC Web Map Service (WMS), we will use the layer name.
      - **`Description`** Description of the online resource
      - **`URL`** URL of the online resource. In case of a geographic standard data services, only the base URL should be provided, without any service parameter.

- **`Metadata standard name`** The name of the geographic metadata standard used to describe the resource. The recommended values are:
  - in the case of vector dataset metadata: ISO 19115 Geographic information - Metadata
  - in the case of grid/imagery dataset metadata: ISO 19115-2 Geographic Information - Metadata Part 2 Extensions for imagery and gridded data
  - in the case of service metadata: ISO 19119 Geographic information - Services

- **`Metadata standard version`** The version of the metadata standard being used. It is good practice to enter the standard’s inception/revision year. ISO standards are revised with an average periodicity of 10-year. Although the ISO TC211 geographic information metadata standards have been reviewed, it is still accepted to refer to the original version of the standard as many information systems/catalogs still make use of that version. The recommended values are:
  - in the case of vector dataset metadata: ISO 19115:2003
  - in the case of grid/imagery dataset metadata: ISO 19115-2:2009
  - in the case of service metadata: ISO 19119:2005

- **`Metadata character set`** The character set encoding used in the dataset.
  - **`Characterset code`**  
  - **`Codelist used`**  

- **`Dataset URI`** A unique resource identifier for the dataset, such as a web link that uniquely identifies the dataset. The use of a Digital Object Identifier (DOI) is recommended.

- **`Metadata maintenance and update frequency`** The metadata maintenance and update frequency elements provide information on the maintenance of the metadata including the frequency of updates. This is a free text element. The information should be chosen from values recommended by the ISO 19139 controlled vocabulary with the following options: continual, daily, weekly, fortnightly, monthly, quarterly, biannually, annually, asNeeded, irregular, notPlanned, unknown.


**IDENTIFICATION** 

**DATASET IDENTIFICATION**

- **`Title`** Title of the resource (dataset, series, or service).

- **`Alternate title`** An alternate title (if applicable)

- **`Collective title`** A title in case the resource is part of a broader resource (e.g., data collection).

- **`Responsible party`**  
  - **`Organisation name`**  
  - **`Individual name`** 
  - **`Email`** 
  - **`Phone`** 
  - **`Physical address`** 
    - **`Delivery point`** 
    - **`City`** 
    - **`Postal code`**  
    - **`Country`** 
  - **`Online resource`** 
    - **`Name`** 
    - **`Description`** 
    - **`URL`** 

- **`Reference dates`** Date(s) associated to a resource. This may include different types of dates. The metadata shall contain a date of publication, revision or creation of the resource.
  - **`Date`** The date, in ISO format.
  - **`Type`** The type of date should be provided, and selected from the controlled vocabulary proposed by the ISO 19139. The following date types will often be used:
    - *Date of publication*: This is the date of publication of the resource when available, or the date of entry into force. There may be more than one date of publication. Date of publication differs from the temporal extent. For example, a dataset might have been published in March 2009 (2009-03-15) but the covered information was collected over the year 2008 (temporal extent from 2008-01-01 to 2008-12-31).
    - *Date of last revision*: This date describes when the resource was last revised, if the resource has been revised. Date of revision differs from the temporal extent. For example, a dataset might have been revised in April 2009 (2009-04-15) but the covered information was collected over the year 2008 (temporal extent from 2008-01-01 to 2008-12-31).
    - *Date of creation*: This date describes when the resource was created. Date of creation differs from the temporal extent. For example, a dataset might have been created in February 2009 (2009-02-15) but the covered information was collected over the year 2008 (temporal extent from 2008-01-01 to 2008-12-31).

- **`Abstract`** This is a brief narrative summary of the content of the resource. The abstract provides a clear and concise statement that enables the reader to understand the content of the data or service.
  RECOMMENDATIONS
  1. The resource abstract is a succinct description that can include:
    - A brief summary with the most important details that summarize the data or service
    - Coverage: linguistic transcriptions of the extent or location in addition to the bounding box
    - Main attributes
    - Data sources
    - Legal references
    - Importance of the work
  2. Do not use unexplained acronyms.
  3. Summarize the most important details in the first sentence or first 100 characters.

- **`Additional information`** Any other descriptive information about the resource that doesn’t fit into other elements​

- **`Topics`** The topic category is a high-level classification scheme to assist in the grouping and topic-based search of available spatial data resources.
  A correct categorization is very important to help users to search and find the resources they are looking for.

- **`Keywords`** 
  - **`Type`** Keywords type. The ISO 19139 provides a recommended controlled vocabulary.
  - **`Keyword`** The keyword itself. When possible, existing vocabularies should be preferred to writing free-text keywords. An example of global vocabulary is the Global Change Master Directory that could be a valuable source to reference data domains / disciplines, or the UNESCO Thesaurus.
  - **`Thesaurus name`** A reference to a thesaurus (if applicable) from which the keywords are extracted. The thesaurus itself should then be documented as a citation.

- **`Resource identifiers`** 
  - **`Identifier`** A value uniquely identifying an object within a namespace.
  - **`Authority`** A unique persistent identifier for the metadata. If a DOI is available for the resource, the DOI should be entered here. The same file identifier should be used if no other persistent identifier is available.

- **`Dataset character set`**
  - **`Codelist value`** The dataset character set has to be documented in ISO 19115 when ISO 10646-1 is not used. This element is mandatory only if an encoding is used that is not based on UTF-8 (the dominant encoding of ISO 10646-1).
  - **`Codelist URI`** 

- **`Dataset language`** The dataset language, defaulted to the language of the metadata. This refers to the language(s) used within the resource (dataset, series, or service if relevant).
  It is recommended to use the alpha-3 codes of ISO 639-2. Use only three-letter codes from in ISO 639-2/B (bibliographic codes, example "eng" for English).
  The list of all the codes is defined at http://www.loc.gov/standards/iso639-2/.
  Regional languages also are included in this list.

- **`Presentation form`** Form in which the resource is made available. The ISO 19139 recommends a controlled vocabulary. For a geospatial dataset or web-layer, the value "Map digital" will be preferred.

- **`Contacts`** This is the description of the person or organization responsible for the establishment, management, maintenance or distribution of the resource. This description shall include at least the name of the organization and contact email address. The name of the organization should be given in full, without abbreviations. It is recommended to use institutional email instead of personal emails.
  - **`Individual name`** 
  - **`Organisation name`**  
  - **`Phone`** 
  - **`Email`**  
  - **`Physical address`** 
    - **`Delivery point`** 
    - **`City`** 
    - **`Postal code`**  
    - **`Country`**  
  - **`Online resource`** 
    - **`Name`**  
    - **`URL`** 
    - **`Description`** 

**SERVICE IDENTIFICATION** (this section applies to services only, not to datasets)

- **`Service type`** The type of service (as free text), e.g., OGC:WMS. This is a classification to assist in the search of available spatial data services.
- **`Service type version`** The version of the service e.g. 1.3.0
- **`Access properties`** 
  - **`Fees`** 
  - **`Service availability date`**  
  - **`Ordering instructions`**  
  - **`Turnaround`**  
- **`Restrictions`**
  - **`Legal constraints`**  
    - **`Use limitation`**  
    - **`Access constraints`**  
    - **`Use constraints`**
    - **`Other constraints`**  
  - **`Security constraints`** 
    - **`Use limitation`** 
    - **`Classification`**  
    - **`Note on security classification`**  
    - **`Classification system`** 
    - **`Handling description`** 

- **`Keywords`** 
    A keyword is defined by:
    - a keyword value ("keyword")
    - an optional originating controlled vocabulary which in ISO standard is referred to as “Thesaurus”. If the keyword value originates from a controlled vocabulary (thesaurus, ontology), for example GEMET - Concepts, 
    the citation of the originating controlled vocabulary shall be provided.
    It is better to select keyword values from a collection of terms linked and predefined (controlled vocabularies).
    RECOMMENDATIONS
    If only one keyword is used, then for spatial dataset or spatial dataset series, the keyword:
    - shall describe the relevant data theme
    - shall be expressed in the language of the metadata
    For example, a keyword that comes from GEMET - Concepts shall be cited as follows:
    - keyword: freshwater
    - thesaurus name: GEMET - Concepts, version 2.4
  - **`Type`** 
  - **`Keyword`** The keyword value is a commonly used word, formalized word or phrase used to describe the subject. While the topic category is too coarse for detailed queries, keywords help narrowing a full text search and they allow for structured keyword search.
  EXAMPLES:
    - Atmospheric conditions (INSPIRE Spatial Data Theme)
    - humanCatalogueViewer (spatial data service subcategory)
    - water springs (AGROVOC)
    - rain water (GEMET Concepts)
  - **`Thesaurus name`** The thesaurus name shall include at least the title and a reference date (date of publication, date of last revision or of creation) of the originating controlled vocabulary. It is important to specify which version of the thesaurus was used to take the keyword value from.

- **`Coupled resource`**  
  - **`Operation name`** 
  - **`Identifier`** 

- **`Coupling type`**  

- **`Operations contained in service`** 
  - **`Operation name`** 
  - **`DCP`** 
  - **`Operation description`** 
  - **`Invocation name`** 
  - **`Parameters`** 
    - **`Name`** 
    - **`Direction`** 
    - **`Description`** 
    - **`Optionality`** 
    - **`Repeatability`** 
    - **`Value type`** 
  - **`Connect point`** 
    - **`Linkage`** 
    - **`Name`** 
    - **`Description`** 
    - **`Protocol`** 
    - **`Function`** 
      
- **`Operates on`** 
    - **`uuidref`** 


**PURPOSE, CREDIT AND STATUS**

- **`Purpose`** A description of why the dataset or resource was created—in other words, its intended use or application.
  Expectations for the "purpose" element:
  - Content: A clear, concise explanation of the rationale behind the dataset's creation. This could include:
    - The objective of the data collection effort.
    - The decision-making context or policy needs the data supports.
    - Specific applications the dataset was designed for (e.g., urban planning, disaster risk assessment).
    - Any targeted users or communities (e.g., researchers, environmental agencies).
  - Format:
    - It is a free-text field.
    - The text should be descriptive, but not excessively long—typically one to a few sentences.
  - Best practices:
    - Avoid jargon; ensure it is understandable to a general audience.
    - Distinguish it from other elements like abstract (which describes the content) or useConstraints (which explains how the data may or may not be used).
    - Be specific enough to support discovery and evaluation by potential users.

- **`Credit`** This element is used to acknowledge individuals, organizations, or agencies that contributed to the creation, funding, or provision of the dataset or resource.
  Expectation:
  - Content: A free-text acknowledgment of contributors, typically including:
    - Data producers
    - Funders or sponsors
    - Collaborating institutions
    - Partner organizations
    - Any person or group whose contribution should be recognized
  - Best Practices:
    - Be accurate and complete—credit all major contributors to avoid disputes or omission.
    - Use formal names of organizations or projects to support discoverability and proper attribution.
    - Do not use this field for legal constraints or licensing

- **`Status`** This element specifies the current state or progress of the dataset or resource. It is a mandatory element in ISO 19115 metadata, as it helps users understand whether the dataset is completed, ongoing, planned, or obsolete.
  Expectation:
  - Content: A code from a controlled vocabulary defined by ISO 19115. The expected value is taken from the MD_ProgressCode code list.
  - Common values include:
    - completed – data collection and processing are finished
    - historicalArchive – no longer maintained but archived for reference
    - obsolete – superseded by a newer dataset
    - onGoing – being continually updated
    - planned – data collection or production is intended but not started
    - required – data is needed but not yet available
    - underDevelopment – in the process of being created
  Best Practices:
  - Use only values from the official code list.
  - Choose the code that best reflects the life cycle stage of the dataset.
  - Be consistent across related metadata records if the status applies to multiple datasets in a series.


**EXTENT (GEOGRAPHIC, TEMPORAL, VERTICAL)**

**`Geographic element`** 
  - **`Bounding box`** This is the extent of the resource in the geographic space, given as a bounding box. Defining the coordinates of a rectangle representing the resource area on a map allows the discovery by geographical area. Provide the coordinates bounding the limits of the dataset, by means of four properties:
    - **`West bound longitude`** Western-most coordinate of the limit of the dataset extent, expressed in longitude in decimal degrees.
    - **`East bound longitude`** Eastern-most coordinate of the limit of the dataset extent, expressed in longitude in decimal degrees.
    - **`South bound latitude`** Southern-most coordinate of the limit of the dataset extent, expressed in latitude in decimal degrees.
    - **`North bound latitude`** Northern-most coordinate of the limit of the dataset extent, expressed in latitude in decimal degrees.
- **`Geohash`**
  - **`Geohash`** 
  - **`Note`** 
- **`Geographic description`** 
- **`Bounding polygon`** 
  - **`Polygon identifier (ID)`** 
  - **`Polygon`** 
    - **`Interior or exterior ring`**  
    - **`Type`** Type of geometry
    - **`Coordinates`** Coordinates of the polygon. The first and last coordinate pairs must be the same to close the polygon.

**`Temporal element`** The temporal extent defines the time period covered by the content of the resource. Depending on the temporal characteristics of the dataset, this will consist in a Time period (made of a begin position and end position) or a time instant (made of a single time position) referencing date/time information according to ISO 8601. This time period may be expressed as an individual date, an interval of dates (starting date and ending date), or a mix of individual dates and intervals of dates.
  - **`beginPosition`** Begin time position. Requires an extended ISO 8601 formatted combined UTC date and time string (2009-11-17T10:00:00)
  - **`endPosition`** End time position. Requires an extended ISO 8601 formatted combined UTC date and time string (2009-11-17T10:00:00)

- **`Vertical element`** Spatial (vertical) extent element, providing two properties: minimum value, maximum value and vertical CRS (reference to the vertical coordinate reference system)
  - **`Minimum value`** 
  - **`Maximum value`** 
  - **`Vertical CRS`** 


**SPATIAL REPRESENTATION AND RESOLUTION** 

- **`Spatial representation type`** The spatial representation type of the dataset. Values should be selected from the following controlled vocabulary: {vector, grid, textTable, tin, stereoModel, video}

- **`Spatial resolution`** The spatial resolution of the data as numeric value associated to a unit of measure. Spatial resolution refers to the level of detail of the data set. It shall be expressed as a set of zero to many resolution distances (typically for gridded data and imagery-derived products) or equivalent scales (typically for maps or map-derived products). An equivalent scale is generally expressed as an integer value expressing the scale denominator. A resolution distance shall be expressed as a numerical value associated with a unit of length.
  - **`Spatial resolution UOM`** Spatial resolution unit of measure 
  - **`Spatial resolution value`**  
    EXAMPLES:
    - 50000 (e.g. 1:50000 scale map)
    - 0.25 (degrees)
  NOTES:
    - For services, it is not possible to express the restriction of a service concerning the spatial resolution in the current version of ISO 19119. While the problem is addressed by the standardization community, spatial resolution restrictions for services shall be expressed in the Abstract.
    - When two equivalent scales or two ground sample distances are expressed, the spatial resolution is an interval bounded by these two values.


**GRAPHIC OVERVIEW**

- **`Graphic overview`** 
  - **`File name`** 
  - **`File description`** 
  - **`File type`** 


**FREQUENCY OF UPDATE**

- **`Frequency`** Maintenance and update frequency
- **`Maintenance note`** Maintenance note.


**SPECIFIC USAGE** 

- **`Resource specific usage`**
  - **`Specific usage`**
  - **`Time (date)`** 
  - **`User determined limitations`**  
  - **`Contacts`** 
    - **`Individual name`** 
    - **`Organisation name`**  
    - **`Email`** 
    - **`Phone`** 
    - **`Address`** 
      - **`Delivery point`** 
      - **`City`**  
      - **`Postal code`** 
      - **`Country`** 
    - **`Online resource`**
    - **`Name`**  
    - **`URL`** 
    - **`Description`** 

    
**LEGAL CONSTRAINTS**

- **`Legal constraints`**
  - **`Use limitation`** 
  - **`Access constraints`** Legal access constraints. The ISO 19139 provides a controlled vocabulary. These are the access constraints applied to assure the protection of privacy or intellectual property, and any special restrictions or limitations on obtaining the resource.
  - **`Use constraints`** Use constraints. To be entered as free text. Filling this element will depend on the resource that is described. As best practice recommended to fill this element, this is where terms of use, disclaimers, preferred citation or* even data limitations can be captured
  - **`Other constraints`** Any other legal restrictions and legal prerequisites for accessing and using the resource or metadata.


**RESOURCE FORMAT`** 

- **`Resource format`** 
  - **`Name`** 
  - **`Version`** 


**REFERENCE SYSTEM**

- **`Reference system`** The reference system(s) typically (but not necessarily) applies to the geographic reference system of the dataset. Multiple reference systems can be listed if a dataset is distributed with different spatial reference systems. This block of elements may also apply to service metadata. A spatial web-service may support several map projections / geographic coordinate reference systems. A reference system is defined by two properties:
    - **`Code`** The identifier of the reference system. The recommended practice is to use to the Spatial Reference IDentifier (SRID) number. For example, the SRID of the World Geodetic System (WGS 84) is 4326.
    - **`Code space`** The code space of the source authority providing the SRID. The best practice is to use the EPSG authority code EPSG (as most of geographic reference systems are registered in it). Codes from other authorities can be used to define ad-hoc projections, for example:
      - ESRI:54012 (Eckert IV equal area projection)
      - EPSG:4326 (World Geodetic System 84 - aka WGS84), the system used for GPS
      - EPSG:3857 (Web Mercator / Pseudo-Mercator) - widely used for map visualization from web map tile providers.
  
  The main reference system registry is EPSG, which provides a “search by name” tool for users who need to find a SRID (global or local/country-specific). Other websites reference geographic systems, but are not authoritative sources including http://epsg.io/ and https://spatialreference.org/ The advantage of these sites is that they go beyond the EPSG registry, and handle other specific registries given by providers like ESRI.

  The following ESRI projections could be relevant, in particular those in support of world equal-area projected maps (maps conserving area proportions):
  - ESRI:54012 (Eckert IV)
  - ESRI:54009 (Mollweide)
  - ESRI:54030 (Robinson)

 
**SPATIAL REPRESENTATION**

- **`Vector data`**
  - **`Topology level`** Topology level is the type of topology used in the vector spatial dataset. The ISO 19139 provides a controlled vocabulary. In most cases, vector datasets will be described as geometryOnly which covers common geometry types (points, lines, polygons).
  - **`Geometric objects`**
    - **`Type`** The type of geometry handled. A controlled vocabulary is used. In the case of an homogeneous geometry type, a single geometricObjectselement can be defined. For complex geometries (mixture of various geometry types), one geometricObjects element will be defined for each geometry type.
    - **`Count`** The number (count) of geometries in the dataset.

- **`Grid data`**
  - **`Number of dimensions`** Number of dimensions in the grid.
  - **`Axis dimension properties`** A list of each dimension including, for each dimension, the name, size, and resolution.
    - **`Name`** The name of the dimension type: the ISO 19139 provides a controlled vocabulary with the following options: row, column, vertical, track, crossTrack, line, sample, and time. These options represent the following:
      - row: ordinate (y) axis
      - column: abscissa (x) axis
      - vertical: vertical (z) axis
      - track: along the direction of motion of the scan point
      - crossTrack: perpendicular to the direction of motion of the scan point
      - line: scan line of a sensor
      - sample: element along a scan line
      - time: duration
    - **`Size`** The length of the dimension.
    - **`Resolution`** The dimension resolution: a resolution number associated to a unit of measurement. This is the resolution of the grid cell dimension. For example:
      - for longitude/latitude dimensions, and a grid at 1deg x 5deg, the ‘row’ dimension will have a resolution of 1 deg and the ‘column’ dimension will have a resolution of 5 deg.
      - for a “vertical” dimension, this will represent the elevation step. For example, the vertical resolution of the mean Ozone concentration between 40m and 50m altitude at a location of longitude x/ latitude y would be 10 m.
      - similar: in case of a spatial-temporal grid, the “time” resolution will represent the time lag (e.g., 1 year, 1 month, 1 week, etc.) between two measures.
    - **`Cell geometry`** The type of geometry used for grid cells. Possible values are: point, area, voxel, and stratum. Most “grids” are commonly area-based, but in principle a grid goes beyond this and the grid cells can target a point, an area, or a volume.
      - point: each cell represents a point
      - area: each cell represents an area
      - voxel: each cell represents a volumetric measurement on a regular grid in a three dimensional space
      - stratum: height range for a single point vertical profile
    - **`Transformation parameter availability`** 


**DATA QUALITY**

- **`Scope`** Scope / hierarchy level targeted by the data quality information section. The ISO 19139 recommends the use of a controlled vocabulary.
  
- **`Report`** 
  - **`Name of measure`** One or more measure names used for the data quality report.
  - **`Measure identification`** Identification of the measure, using a unique identifier (if applicable).
  - **`Measure description`** A description of the measure.
  - **`Evaluation method type`** Type of evaluation method. The ISO 19139 recommends the use of a controlled vocabulary with the following options: directInternal, directExternal, indirect.
  - **`Evaluation method description`** Description of the evaluation method.
  - **`Evaluation procedure`**
    - **`Title`** Citation of the evaluation procedure (as citation element).
    - **`Alternate title`** 
    - **`Date`** 
      - **`Date`** Date time when the report was established.
      - **`Type`** Date type e.g. publication, revision, creation
    - **`Edition`**  
    - **`Edition date`** 
    - **`Identifier authority`**  
    - **`Identifier code`** 
    - **`Date and time`** 
    - **`Responsible party`** 
      - **`Individual name`** 
      - **`Organisation name`** ) 
      - **`Email`**  
      - **`Phone`**
      - **`Address`** 
        - **`Delivery point`**  
        - **`City`** 
        - **`Postal code`** 
        - **`Country`** 
      - **`Online resource`** 
        - **`Name`** 
        - **`URL`** 
        - **`Description`**  
    - **`Resource presentation`**  
  - **Date and time`**
  - **Result of consistency check`**
    - **`Title`** 
    - **`Date`** 
      - **`Date`**  
      - **`Type`** Date type e.g. publication, revision, creation
    - **`Responsible party`** 
      - **`Individual name`** 
      - **`Organisation name`**  
      - **`Email`** 
      - **`Phone`**  
      - **`Address`** 
        - **`Delivery point`** 
        - **`City`** 
        - **`Postal code`** 
        - **`Country`** 
      - **`Online resource`** 
        - **`Name`** 
        - **`URL`** 
        - **`Description`** 
    - **`Resource presentation`** 
    - **`Explanation`** 
    - **`Pass`** Indication of the conformance result. True if conformant ; False if not conformant ; Null (blank) if not evaluated

-**`Lineage`**
  - **`Lineage statement`** Lineage is “a statement on process history and/or overall quality of the spatial data set. Where appropriate it may include a statement whether the data set has been validated or quality assured, whether it is the official version (if multiple versions exist), and whether it has legal validity. The value domain of this element is free text.” This element is not applicable to geographic services.
  
  RECOMMENDATIONS:
  - If a data provider has a procedure for the quality management of their spatial data set (series) then the appropriate ISO data quality elements and measures should be used to evaluate and report (in the metadata) the results. If not, the Lineage metadata element (defined in the Implementing Rules for Metadata) should be used to describe the overall quality of a spatial data set (series).
  - The use of acronyms should be avoided. If used, their meaning should be explained.


**DISTRIBUTION**

- **`Distribution format`** 
  - **`Name`** 
  - **`Version`** 

- **`Distributor`** 
  - **`Individual name`** 
  - **`Organisation name`** 
  - **`Email`** 
  - **`Phone`** 
  - **`Address`** 
    - **`Delivery point`** 
    - **`City`** 
    - **`Postal code`** 
    - **`Country`** 
  - **`Online resource`** 
      - **`Name`** 
      - **`URL`** 
      - **`Description`** 


**FEATURE CATALOGUE**

- **`Name`** Name of the feature catalogue.
- **`Scope`** Subject domain(s) of feature types defined in this feature catalogue.
- **`Fields of application`** One or more fields of applications for this feature catalogue.
- **`Version number`** Version number of this feature catalogue, which may include both a major version number or letter and a sequence of minor release numbers or letters, such as ‘3.2.4a.’ The format of this attribute may differ between cataloguing authorities.
- **`Version date`** Version date in ISO 8601 format.
- **`Version date type`** 
- **`Producer`** 
  - **`Individual name`** 
  - **`Organisation name`** 
  - **`Email`** 
  - **`Phone`** 
  - **`Address`** 
    - **`Delivery point`** 
    - **`City`** 
    - **`Postal code`** 
    - **`Country`** 
  - **`Online resource`** 
      - **`Name`** 
      - **`URL`** 
      - **`Description`** 
- **`Functional language`** Formal functional language in which the feature operation formal definition occurs in this feature catalogue.
- **`Feature type`** 
  - **`Type name`** Text string that uniquely identifies this feature type within the feature catalogue that contains this feature type.
  - **`Definition`** Definition of the feature type.
  - **`Code`** Code that uniquely identifies this feature type within the feature catalogue that contains this feature type.
  - **`Is abstract`** Indicates if the feature type is abstract or not
  - **`Aliases`** One or more aliases as equivalent names of the feature type.
  - **`Carrier of characteristics`** 
    - **`Member name`** Name of the property member of the feature type.
    - **`Definition`** Definition of the property member.
    - **`Cardinality lower`** Definition of the member type cardinality. The cardinality is set of two properties: lower cardinality (lower) and upper cardinality (upper). For simple tabular datasets, the cardinality will be 1-1. Multiple cardinalities (eg. 1-N, N-N) apply particularly to feature catalogues/types that describe relational databases.
    - **`Cardinality upper`** Definition of the member type cardinality. The cardinality is set of two properties: lower cardinality (lower) and upper cardinality (upper). For simple tabular datasets, the cardinality will be 1-1. Multiple cardinalities (eg. 1-N, N-N) apply particularly to feature catalogues/types that describe relational databases.
    - **`Code`** Code for the attribute member of the feature type. Corresponds to the actual column name in an attributes table.
    - **`Measurement unit`** Measurement unit of the values (in case of the feature member corresponds to a measurable variable)
    - **`Value type`** Type of value. A good practice is to rely on primitive data types defined in the XML Schema https://www.w3.org/2009/XMLSchema/XMLSchema.xsd
    - **`Listed values`** List of controlled value(s) used in the attribute member. Each value corresponds to an object compound by 1) a label, 2) a code (as contained in the dataset), 3) a definition. This element will be used when the feature member relates to reference datasets, such as code lists or registers. e.g., list of countries, land cover types, etc.
      - **`Label`** 
      - **`Code`** 
      - **`Definition`**  


**TAGS** 

Tags, especially when organized in tag groups, provide a powerful and flexible solution to enable custom facets (filters) in data catalogs.
  - **`Tag`** A user-defined tag.
  - **`Tag group`** A user-defined group (optional) to which the tag belongs. Grouping tags allows implementation of controlled facets in data catalogs.
    


## Save, export, and use the metadata

Save package
Export ISO 19139
Export JSON
Publish to NADA


