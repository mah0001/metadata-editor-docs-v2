# General instructions

This section provides instructions related to the aspects of data documentation that apply to all data types. Instructions specific to each data type is provided in the subsequent sections.

## The "My projects" page

Every dataset documented in the Metadata Editor is a **project**. A **project** therefore corresponds to a dataset or digital resource that needs to be documented. What a project includes depends on the type of data.
- For microdata, a project is one or a collection of data files, with all related resources.
- For indicators, a project is an indicator (or time series).
- For database, a project corresponds to the "container" of indicators. It includes a list of indicators, but not the indicators themselves.
- For geographic datasets, a project corresponds to one or multiple raster files, or to one or multiple vector data files.
- For research and scripts, a project corresponds to one or multiple scripts and outputs.
- For images, a project corresponds to one image (which may be available in multiple formats and resolutions)
- For videos, a project corresponds to one single video. 

The "My projects" page is accessed by clicking on PROJECTS in the top menu.

See the **Managing projects** section for a detailed description of this page.


## Creating a project

For all data types, the documentation process for a new project consists of: 
1. Creating a project (by clicking on CREATE NEW PROJECT of IMPORT in the *My Projects* page. Refer to the Quick Start examples.
2. Selecting a template for the documentation of the project (optional, as a default template is automatically selected).
3. Populating the metadata fields
4. Adding external resources
5. Adding administrative metadata (optional)
6. Locking and versioning the metadata (optional)
7. Exporting or publishing the metadata

When a project has already been created, its content can be edited by clicking on the project name in the *My projects* page.
  
This work can be made collaborative, by sharing the project with other data curators or publishing the project in one or multiple collection(s); see section **Managing projects** and **Managing collections**. A project will be edited by one or multiple data curators. It may be reviewed, locked and versioned. A system expert may then add administrative metadata (this is usually not done by the data curators; it is a specific  role).


## The project "Home page"

![image](img/ME_UG_v1-0-0_documenting_project_home_page_components.png)


## Title and menu bar

The title and menu bar will display the project title ("untitled" untill you added a project title and saved the metadata), the SAVE button, and a button (triple dots) that opens the project main menu).
The icon shown in from of the proect title indicates the data type of the project.


## Header

The header frame in the *Project home page* provides information on the project identifiers (the editable user-defined primary identifier, and the read-only system-generated unique identifier), on the project owner (typically the project creator, or the user to whom the ownership was transferred), and on the dates the project was created and last modified. The Header also provides an option to select an image (JPG or PNG file) to be used as thumbnail. The thumbnail will be used in the Metadata Editor, and in NADA catalogs if the metadata are published in NADA. 


## Template selection

![image](img/ME_UG_v1-0-0_documenting_general_template_selection.png)

- ***Project template***

  Datasets are documented based o templates. Templates are customized subsets of the metadata elements available from the metadata standard, possibly complemented by user-defined additional elements (refer to the **Templates** section). The template will determine what data curators see in the navigation tree of the Project pages, and the metadata entry pages. A default template is automatically selected when a new project is created (the template to be used as default is selected by the system administrator; see **Designing templates**). 

  The data curator can select another template available in the Metadata Editor. The list of available templates is also selected by the system administrator. 

  Changing the template used for an existing project will NOT impact the content of the metadata that has already been entered. No information is lost when a less comprehensive template is selected; all metadata already captured is preserved, even if it is not displayed when the new template is used. 

- ***Administrative metadata templates***

  Select one or multiple administrative metadata templates (optional). See **Administrative** metadata below, and *Administrative metadata templates* in **Designing templates** for more information on the purpose and use of administrative metadata.


## Navigation tree

The navigation tree shown in the Project page reflects the content of the selected templates. In a template, metadata elements can be tagged as *required* or *recommended*. The navigation frame provides an option to filter elements, to display only required fields or recommended fields. It also provides an option to only display **empty fields**, i.e. metadata elements for which no content has been provided.

A search box is also provided, allowing users to search a metadata element based on keywords found in the element label.


## Project validation ##

The Project home page contains a frame titled **Project validation**, which will indicate whether the metadata that has been entered and saved violates some of the requirements of the standard itself or of the validation rules defined in the template used to document the dataset.

![image](img/ME_UG_v1-0-0_documenting_general_project_validation.png)

- ***Schema validation*** lists the violations of requirements of the metadata standard.
- ***Template validation*** lists the violations of custom validation rules defined in the metadata template.

Clicking on a validation error will take you to the element that needs to be edited.


## Collaborators ##

The frame **Collaborators** in the project Home page will show the list of collaborators who have access to the project, with information on their permission level (View, Edit, Admin, Owner). If you are the owner or administrator of the project, you may edit this list (adding or removing collaborators) from the list by clicking on the icon on top of the frame.

![image](img/ME_UG_v1-0-0_documenting_general_collaborators.png)


## Collections ##

The frame **Collections** in the project Home page will show the list of collections to which the project belongs. If you are the owner or administrator of the project, you may edit this list (adding or removing collections) from the list by clicking on the icon on top of the frame.


## File manager ##

![image](img/ME_UG_v1-0-0_documenting_general_files_documentation.png)

![image](img/ME_UG_v1-0-0_documenting_general_files_list.png)



## Common elements in the navigation tree 

***Home and preview***


***Information on metadata (or Document description)***


***Tags***

All metadata standards and schemas supported by the Metadata Editor include a **Tags** element (this element is not part of all standards; it has been added to standards that did not include it). This element enables the implementation of filters (facets) in data cataloguing applications, in a flexible manner. The tags metadata element is repeatable (meaning that more than one tag can be attached to a dataset) and contains two sub-elements to capture a tag (word or phrase), and the tag_group (if any) it belongs to.

To illustrate the use of tags, let’s assume that you want to indicate whether a dataset is available free of charge or for a fee, and another tag that indicates whether the dataset meets differebntial privacy or not. None of the metadata schemas contains an element specifically designed to indicate the “free” or “for a fee” nature of the dataset, or "differentially private" or not. But this information can be captured in a tag “Free” or “For a fee” within a tag group that could be named “free_or_fee”, and "Differentially private" or "Not differentially private" in a tag group that could be named "differential_privacy". This information becomes part of the metadata, abd can be used by catalog administrators to create customized filtering options (facets) in their user interfaces. 

![image](img/ME_UG_v1-0-0_documenting_general_tags.png)


***External resources***

**External resources** are not a specific type of data. They are resources of any type (data, document, web page, or any other type of resource that can be provided as an electronic file or a web link) that can be attached as a "related resource" to a catalog entry. A metadata schema that is intentionally kept very simple, based on the Dublin Core standard, is used to describe these resources. 

The table below shows some examples of the kind of external resources that may be attached to the metadata of different data types.

| Data type          | Examples of resources that may be documented and published as external resources  |
| ------------------ | ------------------------------------------------------------ |
| Document           | MS-Excel version of tables included in a publication ; PDF/DOC version of the publication ; visualizations files (scripts and image) for visualizations included in the publication ; link to electronic annexes |
| Microdata          | survey questionnaire ; survey report ; technical documentation (sampling, etc.) ; data entry application ; survey budget in Excel ; microdata files in different formats ; link to an external website|
| Geographic dataset | link to an interactive web application ; technical documentation in PDF ; data analysis scripts ; publicly accessible data files |
| Time series        | link to a database query interface ; technical documents ; link to external websites ; visualization scripts |
| Tables             | link to an organization website ; tabulation scripts | electronic copy of the table |
| Images             | image files in different formats and resolutions ; link to a photo album application ; link to a photographer website |
| Audio recordings   | audio file in MP3 or other format ; transcript in PDF |
| Videos             | video file in WAV or other format ; transcript in PDF |
| Scripts            | publication ; link to a package/library web page ; link to datasets | 

To add an external resource, click on *External resources* in the navigation tree. This will open the **External resource** page which lists all external resources already added. The click on CREATE RESOURCE. This will open a new page, where information on the resource can be added. Enter at least the title, type, and upload a file or provuide a URL. Then SAVE.

The *Resource type* element is very important; it will determine how the resource is published in a NADA catalog. Particular attention must be paid to resources of type *Microdata*. When publishing the resource in a NADA catalog, resources of type *Microdata* will not automatically be made available to users of the catalog; the access policy selected when publishing the project in NADA will apply. This could be "Open data" or "Direct access", which will make the data downloadable without restriction, but it could be another access policy such as "Licensed access" which would require that users request access to the data. 

***Data Cite***

DataCite is a service that offers Fabrica as a DOI and metadata management service allowing organizations to register and manage DOIs for their data products (see https://datacite.org/create-dois/). With Fabrica, organizations can assign DOIs, maintain accurate and FAIR metadata, and ensure persistent links for long-term accessibility and citation of their valuable research outputs. Generating a DOI requires that a core set of metadata be provided to the DOI registration service. This section of the navigation tree contains the elements that are needed for that purpose. This section is only used when you plan to issue a DOI for the dataset. 

![image](img/ME_UG_v1-0-0_documenting_general_data_cite.png)

***Provenance***


***Administrative metadata***

**Administrative metadata** will only appear in the navigation tree if administrative metadata templates have been selected in the **Template selection**. Administrative metadata consists of information needed by systems or systems administrators to determine how a dataset should be published in a particular data dissemination platform. This information is not intended to be used or visible by the data users; they only serve an internal purpose for the organization that crates the data. For that reason, when a project metadata is exported, administrative metadata is by default not included. 

The content of the administrative metadata is determined by the administrative metadata template(s) selected for the project. If the project (meta)data is intended to be published in multiple platforms, multiple templates will be used for the project.

The content of the administrative metadata section is not intended to be entered by data curators. They will typically be entered by system administrators. Entering administrative metadata therefore requires a specific riole/permission (see *Setting roles and permissions**).


## Options menu ##

Some elements apply to all data types, some are specific to the data type.

![image](img/ME_UG_v1-0-0_documenting_general_project_main_menu.png)

- ***Export package*** A project contains the metadata you enter, the data files you may have imported (for microdata), the project thumbnail, and possibly external resources of different types. The Metadata Editor stores this information in a database and on the webserver that hosts the Editor. You may export a *package* that contains all materials related to the project. This package will consist of a ZIP file containing all files (including the metadata you entered, even if you did not export them). The ZIp file can be archived, or shared. A package can be imported in the Metadata Editor.     

- ***Export DDI Codebook*** This option ony applies to project of type *microdata*. It will generate a DDI Codebook file (XML format) containing the metadata, **not including** the external resources. 

- ***Export JSON*** This option applies to project of all types. It will generate a metadata file in JSON format. The file will contain the core metadata and other components based on the options you will select: including external resources, including metadata elements marked as *private* in the metadata template,  and including the administrative metadata.

  ![image](img/ME_UG_v1-0-0_documenting_general_json_export_options.png)

- ***Export MSD (SDMX/XML 3.0)*** (applies to project of type *indicator* only)

- ***Export Metadataset (SDMX/JSON)*** (applies to project of type *indicator* only)

- ***Lock & version** 

- ***Publish to NADA*** This option allows you to publish your metadata (and related materials, optionally including data) to a NADA catalog. See chapter **Publish to NADA** for more information.

- ***PDF documentation*** This option will generate a formatted PDF document containing the project metadata.

- ***Change log*** This option will open a page that shows all actions taken o the project, with identification of who took the action (change log). This option can be used to undo some actions.
    
  ![image](img/ME_UG_v1-0-0_documenting_general_change_log.png)

  ![image](img/ME_UG_v1-0-0_documenting_general_change_log_example.png)

- ***Diagnostic***

- ***Applying default values from template*** If the template used for documenting the dataset contains default values, this option will allow you to apply them to your project. Default values are not imputed in a project unless this option is selected. When you apply default value, you will be offered to apply default values to all metadata elements for which a default value exists, or only to metadata elements that do not contain any information (this option will protect information you may have entered against overwriting).

  ![image](img/ME_UG_v1-0-0_documenting_general_apply_default_values_options.png)
  
- ***Import project metadata*** This option will allow you to select a metadata file (JSON) and import its content in your project. For microdata, you will be provided with an option to select the components of the metadata you want to import.

  ![image](img/ME_UG_v1-0-0_documenting_general_import_project_metadata.png)

- ***Import external resources*** This option allows you to import an external resource that has been exported from another project as a RDF/JSON file (see below). Select the RDF/JSON file and click IMPORT FILE.

- ***Export RDF/XML*** This option will export the metadata related to the external resources as an RDF/XML file.

- ***Export RDF/JSON*** This option will export the metadata related to the external resources as an RDF/JSON file.


## Help ##

The metadata entry pages will show a [?] icon next to the title of all metadata elements. Clicking on this icon will show the instructions for the element, extracted from the selected metadata template.

![image](img/ME_UG_v1-0-0_documenting_general_help_button.png)


## Canceling changes (Undo) ##

![image](img/ME_UG_v1-0-0_documenting_general_cancel_changes.png)


