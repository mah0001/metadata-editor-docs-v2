# About

The Metadata Editor is a powerful and flexible open-source application designed to streamline the documentation of data of diverse types, including statistical indicators, survey microdata, geographic raster and vector datasets, documents, images, videos, scripts, and more. It enables users to generate rich, structured metadata that complies with international metadata standards and schemas. Additionally, the application is designed for extensibility, allowing users to integrate new standards, schemas, and updated versions as they emerge.

The Metadata Editor is a tool used by data curators to generate rich and structured metadata. These metadata, typically saved as JSON or XML files, serve as input to data cataloguing and dissemination systems.     

The Metadata Editor can be deployed as a stand-alone desktop application or as a server-based tool, supporting collaborative metadata curation within research institutions, statistical agencies, data repositories, and digital libraries. When operated on a server, it facilitates multi-user collaboration, version control, and centralized metadata management, enhancing the efficiency and consistency of documentation workflows.

Built with a modular architecture, the Metadata Editor is developed using PHP and leverages APIs for seamless integration with other data systems. It incorporates Python libraries such as Pandas and GeoPandas to support the ingestion of datasets in various formats, extract metadata automatically, and generate summary statistics, making metadata creation both efficient and precise.

**Data Types and Metadata Standards Supported**

The Metadata Editor supports the documentation of a wide range of structured data types, using established metadata standards and schemas:

- **For Structured Data**
   - **Microdata**: Unit-level data on individuals, households, facilities, establishments, or other entities, derived from surveys, censuses, administrative records, or sensors. The Metadata Editor supports documentation using the Data Documentation Initiative (DDI) Codebook standard (version 2.5).
   - **Indicators and Databases of Indicators**: Summary measures derived from observed data, often stored as time series in databases. The Metadata Editor supports a bespoke World Bank metadata schema, built by compiling metadata elements used in multiple leading indicator databases.
   - **Geographic Datasets and Geographic Data Services**: Data describing geographic locations, boundaries, and earth surface characteristics, provided as raster or vector datasets or as web services. The Metadata Editor supports ISO 19139 (and related ISO 19110/19115) metadata standards.
   - **Statistical Tables**: Aggregated statistical information presented in cross-tabulations, such as those in statistical yearbooks and census reports. The Metadata Editor supports a specific metadata schema developed by the International Household Survey Network (IHSN).

- **For Unstructured Data**
   - **Text**: Collections of documents (e.g., books, reports, manuals) form corpora that can be structured using natural language processing (NLP). The Metadata Editor supports a schema combining elements from Dublin Core, MARC21 (Library of Congress), and BibTeX.
   - **Images**: Digital images can be analyzed with machine learning techniques for classification and object detection. The Metadata Editor provides two metadata schema options: Dublin Core with imageObject elements from Schema.org and IPTC.
Video Recordings: Speech-to-text algorithms allow the automatic transcription of video and audio recordings, making them discoverable and analyzable as structured data. The Metadata Editor supports a schema incorporating elements from Dublin Core and videoObject from Schema.org.
   - **Research Projects and Scripts**: Research projects and related scripts for data transformation, analysis, and visualization are essential for reproducibility and transparency. The Metadata Editor includes a dedicated schema for documenting research projects and scripts.

## Acknowledgments

The Metadata Editor application was developed by Mehmood Asghar (Senior Data Engineer, World Bank, lead developer) with Olivier Dupriez (Deputy Chief Statistician, World Bank, project manager). 

The application was in part inspired by the Nesstar Publisher software application (by the Norwegian Social Science Data Archive). 

The application benefited from feedback from many colleagues who reviewed and tested it, including Tefera Bekele, Cathrine Machingauta, Rochelle O'Hagan, and Matthew Welch. 

A team at Outsourcify Ltd (Thailand) supported the development of the user interface. 
