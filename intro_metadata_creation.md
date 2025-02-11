# Production of standard-compliant metadata

Standard-compliant metadata can be produced and edited through two methods: using a Metadata Editor software application or programmatically.

**Using a Metadata Editor**

A metadata editor is specialized software designed to facilitate the creation of structured metadata in a user-friendly manner, particularly beneficial for non-programmers and for specific data types like microdata. The World Bank provides its own Metadata Editor application, accessible to both internal staff and external users.

Users initiate dataset documentation by selecting a data type (e.g., indicator, geographic dataset, microdata, or scripts) and choosing from available templates. Metadata entry forms are then automatically generated based on the selected template, enabling users to input and save metadata in a standard-compliant format (JSON, XML). A brief overview of this proves is provided in Annex 2. Metadata produced by the Metadata Editor can then be published in data catalogs and converted into various formats such as PDF or HTML.

Some data types like microdata or geographic datasets have metadata embedded in the data files themselves (e.g., microdata files contain the variable names, variable labels, and value labels needed to generate the data dictionary). Such metadata can be extracted automatically using tools provided by the Metadata Editor. Detailed instructions are available in the application's User's Guide.

**Programmatically**

Metadata compliant with the standards can be programmatically generated using R lists or Python dictionaries that adhere to the structure outlined in [ReDoc URL]. The programmatic approach offers increased flexibility and efficiency. It enables automation of metadata generation processes and facilitates the utilization of advanced machine learning techniques for automatic metadata enhancement. 

***Other standard-compliant software applications***

Metadata standards may be integrated by software developers into data management systems and tools, such as the Survey Solutions software developed by the World Bank or CsPro developed by the US Census Bureau, which includes a function for exporting metadata compliant with the DDI Codebook metadata standard. Such applications will typically only generate a subset of the metadata elements needed to document a dataset (Survey Solutions and CsPro, for example, will only generate the file and variable-level information). The metadata exported from such applications can be edited and completed using the Metadata Editor.

