# Introduction to metadata standards

Data producers who seek to ensure that their data are discoverable, visible, and usable must provide data users with rich and structured metadata—information that elucidates the context, quality, and characteristics of the underlying data. Rich and structured metadata not only enhance the trustworthiness of the data but also enable advanced search functionalities that empower users to locate, assess, utilize, and repurpose the data effectively and responsibly. 

## Metadata

Metadata refers to information that describes, explains, locates, or otherwise makes it easier to retrieve, use, or manage data.  It includes cataloguing, contextual, and explanatory information.

- ***Cataloguing information*** includes elements such as the title of the dataset, its unique identifier, and its version number. It allows the dataset to be uniquely identified within a collection or catalog and serves as a bibliographic record of the dataset.
- ***Contextual information*** describes the context in which the data were collected (including its geographic and temporal coverage) and used. It enables secondary users to understand the background and processes behind the data production.
- ***Explanatory materials*** consist of information that must be created and preserved to ensure the long-term functionality of a dataset, including for example a data dictionary.

***Rich metadata*** means metadata that is detailed and comprehensive. What makes metadata “detailed and comprehensive” is not always easy to define, and is specific to each data type. Microdata and geospatial datasets for example will require much more – and different– metadata than a document or an image. Metadata standards and schemas provide data curators with detailed lists of elements (or fields), specific to each data type, that must or may be provided to document a dataset. The metadata elements included in a standard or schema will typically cover cataloguing material, contextual information, and explanatory materials.

***Structured metadata*** means that the metadata are stored in specific fields (or elements) organized in a metadata schema. Standardized means that the list and description of elements are commonly agreed by a community of practice, in which case the metadata schema is referred to as a metadata standard. Some metadata schemas may be standard within an organization, others may be adopted by a larger community of practice, in some cases internationally. International metadata standards have particular value as they facilitate the sharing of international good practice and support cost-effective and efficient data and metadata exchange.

## Metadata standards

### Description and rationale

A metadata standard comprises an organized set of clearly defined elements designed for documenting a dataset, accompanied by rules and instructions to ensure their uniform and consistent implementation. A specific metadata standard is developed for each main type of development data.

Some metadata standards have originated from academic data centers, like the Data Documentation Initiative (DDI), maintained by the Inter-University Consortium for Political and Social Research (ICPSR) at the University of Michigan. Other found their origins in specialized communities of practice (like the ISO 19139 for geospatial resources). The private sector also contributes to the development of standards, like the International Press Telecommunications Council (IPTC) standard developed by and for news media.

Metadata standards are conventionally delineated in JSON or XML formats, with JSON being the favored format within the framework of the World Bank's metadata standardization efforts. The metadata elements in a standard are typically arranged hierarchically. The description of the metadata standards is available at [redoc url], where the detailed structure of each standard and information on each element is provided.

image here

Adopting **metadata standards** represents a pragmatic and efficient strategy to augment the comprehensiveness, usability, discoverability, and interoperability of the metadata:

- ***Completeness of metadata***: Metadata standards and schemas provide exhaustive checklists of required or recommended information for documenting datasets. Adherence to these standards ensures that essential information is systematically included, mitigating the risk of oversight.
- ***Usability of data***: Structured metadata enhances the accessibility and usability of data, simplifying user engagement and analysis processes.
- ***Discoverability of data***: Rich and structured metadata facilitates advanced indexing and search functionalities, bolstering the discoverability of datasets across diverse platforms and repositories.
- ***Interoperability***: Metadata standards promote interoperability among data catalogs, enabling seamless information exchange through automated harvesting and synchronization mechanisms (APIs). 

Each element within a metadata standard encompasses:

- ***Key***: This denotes the standardized name assigned to the element and must remain constant.
- ***Type***: Metadata elements can encompass various data types such as text (string), numerical values (numeric), arrays, or Boolean values (logical). In cases where an element is an array, its sub-elements can inherit any of these types. The type of an element is predetermined within the standard and remains constant.
- ***Label***: A concise description or title associated with the element. Although each element or sub-element comes with a default label, the label can be customized.
- ***Repeatable status***: Indicates whether the element can accept multiple entries. For instance, the "nation" element, denoting the countries covered by a dataset, is repeatable, while the "title" element is not. This feature is defined within the standard and remains unalterable.
- ***Requirement status***: Specifies whether the element is mandatory or optional. A "recommended" status may also be included. While it is advised to populate as many metadata elements as feasible, standards should accommodate situations with incomplete metadata. Within the World Bank standards, only a handful of elements are designated as "required," including the unique identifier (preferably a global unique identifier like a DOI), title, authoring entity, and geographic coverage. The descriptor "World" is utilized when a resource lacks specific geographic coverage.
- ***Description***: Each element within the metadata standards is accompanied by a default description and instructions for data curators. These descriptions and instructions are customizable.
- ***Controlled vocabularies***: Controlled vocabularies offer a predefined list of acceptable values for certain elements. This feature assists in maintaining consistency and coherence within metadata content. Controlled vocabularies may be embedded in the standards. In most cases however, they will be specific to an organization and are better embedded in customized templates (see section Implementation).

Examples:

The metadata elements provided in the DDI Codebook metadata standard to store the title of a micro-dataset and the list of countries the dataset refers to are as follows:

- *Key:*	title
- *Type:*	String
- *Label:*	Title
- *Repeatable status:*	Not repeatable
- *Required:*	Yes
- *Controlled vocabulary:*	None
- *Description:*	The official name of the survey (or dataset) as it is stated on the questionnaire or as it appears in the design documents. The following items should be noted:

  - Include the reference year(s) of the survey in the title.
  - Do not include the abbreviation of the survey name in the title.
  - As the survey title is a proper noun, the first letter of each word should be capitalized (except for prepositions or other conjunctions).
  - Including the country name in the title is optional.


- *Key:*	Nation
- *Type:*	Array, with two sub-elements: name (string), and abbreviation (string)
- *Label:*	Countries
- *Repeatable status:*	Yes
- *Required:*	Yes
- *Controlled vocabulary:*	ISO country list and codes (alpha 3)
- *Description:*	Indicates the country or countries covered in the file. Field abbreviation may be used to list common abbreviations; use of ISO country codes is recommended. Maps to Dublin Core Coverage element. Inclusion of this element is recommended.


### Metadata standards supported by the Metadata Editor

The schemas or standards implemented in the Metadata Editor are the following: 

| Data type                  | Standard                                        | 
| -------------------------- | ----------------------------------------------- | 
| Documents                  | Dublin Core Metadata Initiative (DCMI), MARC    | 
| Microdata                  | Data Documentation Initiative 2.5 (Codebook)    | 
| Geographic datasets and services | ISO 19110, ISO19115, ISO19119, ISO 19139  | 
| Time series, Indicators    | Custom-designed schema                          | 
| Statistical tables         | Custom-designed schema                          | 
| Photos / Images            | IPTC (for advanced use) or Dublin Core augmented| 
| Audio files                | Dublin Core augmented with AudioObject from schema.org | 
| Videos                     | Dublin Core augmented with VideoObject from schema.org | 
| Programs and scripts       | Custom-designed schema                          | 
| External resources         | Dublin Core                                     |


### Production of standard-compliant metadata

Standard-compliant metadata can be produced and edited through two methods: using a Metadata Editor software application or programmatically.

**Using a Metadata Editor**

A metadata editor is specialized software designed to facilitate the creation of structured metadata in a user-friendly manner, particularly beneficial for non-programmers and for specific data types like microdata. The World Bank provides its own Metadata Editor application, accessible to both internal staff and external users.

Users initiate dataset documentation by selecting a data type (e.g., indicator, geographic dataset, microdata, or scripts) and choosing from available templates. Metadata entry forms are then automatically generated based on the selected template, enabling users to input and save metadata in a standard-compliant format (JSON, XML). A brief overview of this proves is provided in Annex 2. Metadata produced by the Metadata Editor can then be published in data catalogs and converted into various formats such as PDF or HTML.

Some data types like microdata or geographic datasets have metadata embedded in the data files themselves (e.g., microdata files contain the variable names, variable labels, and value labels needed to generate the data dictionary). Such metadata can be extracted automatically using tools provided by the Metadata Editor. Detailed instructions are available in the application's User's Guide.

**Programmatically**

Metadata compliant with the standards can be programmatically generated using R lists or Python dictionaries that adhere to the structure outlined in [ReDoc URL]. The programmatic approach offers increased flexibility and efficiency. It enables automation of metadata generation processes and facilitates the utilization of advanced machine learning techniques for automatic metadata enhancement. 

***Other standard-compliant software applications***

Metadata standards may be integrated by software developers into data management systems and tools, such as the Survey Solutions software developed by the World Bank or CsPro developed by the US Census Bureau, which includes a function for exporting metadata compliant with the DDI Codebook metadata standard. Such applications will typically only generate a subset of the metadata elements needed to document a dataset (Survey Solutions and CsPro, for example, will only generate the file and variable-level information). The metadata exported from such applications can be edited and completed using the Metadata Editor.


