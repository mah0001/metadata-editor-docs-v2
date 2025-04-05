# Administrative metadata

Administrative metadata refers to the metadata required for managing and operating data management and dissemination systems. Unlike metadata intended for data users, administrative metadata is primarily used internally and is not shared externally. It contains essential instructions that guide software applications, such as data catalogs, in handling data storage, display, and accessibility parameters. Administrative metadata contribute to ensuring data governance principles and procedures, adherence to privacy protection rules, and compliance with the Bank’s Access to Information Policy (by including metadata on information classification of data assets, in particular flagging restricted and confidential information).

A single dataset may be published across multiple catalogs or data systems, each with distinct administrative requirements. For example, the Bank maintains two versions of its Microdata Library: an internal version and an external version. While the descriptive and structural metadata remain consistent across both versions, the data access conditions differ. Administrative metadata is system-specific and provides tailored instructions for each platform where the data and metadata are published.

The creation of administrative metadata follows a structured approach similar to that of descriptive metadata. A predefined set of metadata elements forms a structured template, which is developed based on the technical requirements of the system. These elements are defined by IT specialists to ensure alignment with system functionalities and operational needs.

Administrative metadata is created and managed within the Metadata Editor, where each dataset (or project) can be assigned one or more administrative metadata templates. These templates ensure consistency and facilitate efficient data management across multiple systems.

A specific type of administrative metadata, known as display metadata, is used to control how datasets are presented within the system. Display metadata is derived from administrative metadata schemas and ensures that data is displayed in accordance with system requirements.

Administrative metadata is securely stored within the system but is not included when metadata is exported for public use. Instead, it remains accessible via APIs, allowing data management and dissemination systems to retrieve and utilize it as needed.
