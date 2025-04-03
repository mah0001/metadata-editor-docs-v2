# About

The Metadata Editor is an open-source application designed to streamline the documentation of data of diverse types, including statistical indicators, survey microdata, geographic raster and vector datasets, documents, images, videos, scripts, and more. It enables users to generate rich, structured metadata that complies with international metadata standards and schemas. Additionally, the application is designed for extensibility, allowing users to integrate new standards, schemas, and updated versions as they emerge.

The Metadata Editor is a tool used by data curators to generate rich and structured metadata. These metadata, typically saved as JSON or XML files, serve as input to data cataloguing and dissemination systems.     

The Metadata Editor can be deployed as a stand-alone desktop application or as a server-based tool, supporting collaborative metadata curation within research institutions, statistical agencies, data repositories, and digital libraries. When operated on a server, it facilitates multi-user collaboration, version control, and centralized metadata management, enhancing the efficiency and consistency of documentation workflows.

Built with a modular architecture, the Metadata Editor is developed using PHP and leverages APIs for seamless integration with other data systems. It incorporates Python libraries such as Pandas and GeoPandas to support the ingestion of datasets in various formats, extract metadata automatically, and generate summary statistics, making metadata creation both efficient and precise.

## Data types and metadata standards supported

The Metadata Editor supports the documentation of a wide range of structured data types, using established metadata standards and schemas:

- **For structured data**
   - **Microdata**: Unit-level data on individuals, households, facilities, establishments, or other entities, derived from surveys, censuses, administrative records, or sensors. The Metadata Editor supports documentation using the Data Documentation Initiative (DDI) Codebook standard (version 2.5); see https://ddialliance.org/ddi-codebook.
   - **Indicators and databases of indicators**: Summary measures derived from observed data, often stored as time series in databases. The Metadata Editor supports a bespoke World Bank metadata schema, built by compiling metadata elements used in multiple leading indicator databases.
   - **Geographic datasets and geographic data services**: Data describing geographic locations, boundaries, and earth surface characteristics, provided as raster or vector datasets or as web services. The Metadata Editor supports ISO 19139 (and related ISO 19110/19115) metadata standards. See https://www.iso.org/standard/67253.html
   - **Statistical tables**: Aggregated statistical information presented in cross-tabulations, such as those in statistical yearbooks and census reports. The Metadata Editor supports a specific metadata schema developed by the International Household Survey Network (IHSN).

- **For unstructured data**
   - **Text**: Collections of documents (e.g., books, reports, manuals) form corpora that can be structured using natural language processing (NLP). The Metadata Editor supports a schema combining elements from Dublin Core (https://www.dublincore.org/), MARC21 from the US Library of Congress (https://www.loc.gov/marc/bibliographic/), and BibTeX (https://www.bibtex.org/).
   - **Images**: Digital images can be analyzed with machine learning techniques for classification and object detection. The Metadata Editor provides two metadata schema options: Dublin Core with imageObject elements from Schema.org and IPTC (https://iptc.org/).
Video Recordings: Speech-to-text algorithms allow the automatic transcription of video and audio recordings, making them discoverable and analyzable as structured data. The Metadata Editor supports a schema incorporating elements from Dublin Core and videoObject from Schema.org (https://schema.org/).
   - **Videos**: the Metadata Editor uses a metadata schema built on videoobject from schema.org.
   - **Research projects and scripts**: Research projects and related scripts for data transformation, analysis, and visualization are essential for reproducibility and transparency. The Metadata Editor includes a dedicated schema for documenting research projects and scripts.

In addition to these metadata standards and schemas, the Metadata Editor allows exporting metadata templates as SDMX Metadata Structure Definitions and the metadata themselves as SDMX metadatasets. An option to export metadata to schema.org (https://schema.org/), Croissant (https://github.com/mlcommons/croissant), and DCAT (https://www.w3.org/TR/vocab-dcat-3/) is also provided for some types of data.

The technical documentation of the metadata standards supported by the Metadata Editor is available at https://worldbank.github.io/metadata-schemas/ where structures and information on each metadata element are provided.


## Licenses and disclaimer 


### Software license
  
The Metadata Editor is published as open-source software under the MIT License (https://opensource.org/license/mit) with the following additional qualifications related to the World Bank's Privileges and Immunities:

*provide text of IGO here*


### User Guide license 

This User Guide is licensed under the Creative Commons Attribution 4.0 International license (CC BY 4.0). See [https://creativecommons.org/licenses/by-nc-nd/4.0/ ](https://creativecommons.org/licenses/by/4.0/)

![image](img/ME_UG_v1-0-0_introduction_cc_by_logo.png)


### Disclaimer

The Metadata Editor is provided "as is", without any warranties or guarantees, express or implied. The World Bank makes no representations regarding the accuracy, reliability, completeness, or suitability of the software for any particular purpose. Users assume full responsibility for the installation, configuration, and use of the application. The World Bank shall not be liable for any direct, indirect, incidental, consequential, or special damages arising from the use or inability to use the software. By using the Metadata Editor, users acknowledge and accept that they are solely responsible for ensuring that their use of the application complies with applicable laws, policies, and data governance requirements. Nothing herein shall constitute or be considered to be a limitation upon or a waiver of the privileges and immunities of any of the member institutions of The Work Bank Group, which are specifically reserved.


## Use of AI

AI was used in the development of this User Guide. Content drafted by the authors was submitted to ChatGPT (with GPT-4o or GPT 3.5) for copy editing, with a prompt to "Please improve the following draft of a section on [...] of the user guide of a specialized metadata editor software application." Additionally, Microsoft Copilot was also used to assiste in refining the text through its *Rewrite* function. No confidential or restricted information was uploaded on ChatGPT. The AI-generated text was reviewed and edited by the author(s) to ensure accuracy.
