# Purpose of templates

## Simplifying the use of metadata standards

Metadata standards include more metadata elements than needed by any user for documenting a specific dataset. The reason is that standards are developed to address many use cases and meet the needs of diverse organizations. To simplify their usage, **metadata templates** are created and used. Metadata templates are tailored subsets of the metadata standard's elements, designed for particular purposes or user groups while maintaining compliance with the standard. Metadata templates allow for customization in several dimensions:
- ***Label:*** The labels provided in the metadata standard can be replaced with labels that conform to the Bank's lexicon or stipulations.
- ***Status:*** Metadata elements can be designated as required or recommended. Declaring a metadata element as required will not prevent the metadata from being saved when no content is provided, but it will prevent it from being validated by applications that require such validation. It serves as a useful quality control. Only a minimal number of elements are required in the metadata standards themselves. Elements not required by the standard can be designated as required in the templates. It is however advised against making numerous elements mandatory and to label those not crucial for the functioning of the data management system as recommended rather than required.
- ***Description/Instructions:*** Tailored descriptions and instructions can be provided for each metadata element. These descriptions can be compiled and used to produce the guidelines to data curators.
- ***Controlled vocabularies:*** Controlled vocabularies can be specified for some metadata elements. These controlled vocabularies must adhere to standardized code lists utilized at the Bank. See section 3.3.2.
- ***Default values:*** Default values can be provided for selected elements, albeit these are infrequently utilized.
- ***Validation rules:*** Customized validation rules can be set, using regular expressions, value ranges, or others, to guarantee metadata coherence and uniformity.
- ***Adding elements:*** Elements that are not part of a standard can be added in templates (see section 3.4). 

These various customization options help tailor standards to specific use cases. They also enable the creation of templates in different languages. The Metadata Editor provides a Template Manager tool to generate such templates. 

## Embedding controlled vocabularies in the metadata standards

A **controlled vocabulary**, also known as a **code list**, is a predefined and structured set of terms (with corresponding codes) that are consistently used to populate specific metadata elements. Controlled vocabularies are applied to a limited number of elements within a metadata standard to ensure uniformity and precision.

Utilizing controlled vocabularies helps ensure that the same concept is consistently represented by the same term across various records, thereby reducing ambiguity and enhancing searchability and interoperability. Examples of controlled vocabularies include widely recognized national and international classifications, such as ISO country codes and names or the International Standard Industrial Classification (ISIC). Additionally, they may comprise organization-specific vocabularies, such as keyword taxonomies or tailored code lists designed for specific domains or purposes.  

Controlled vocabularies play a critical role in data discovery. By applying standardized terms to metadata elements, data catalogs can offer these terms as filtering options (facets), allowing users to narrow their search based on specific attributes or categories. This approach significantly enhances the discoverability of datasets, facilitating a more efficient search experience.

## Defining schemas for administrative metadata

Administrative metadata is the metadata needed for the administration of specific data management and dissemination systems. As the requirements of such systems vary widely, no pre-defined standard or schema is provided. Templates are used in the Metadata Editor to define the content of administrative metadata schemas, fully tailored to the needs of the systems in place in the organization that uses the Metadata Editor. 
