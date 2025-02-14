# Quick start: Geographic dataset

In this example, we will document a geographic dataset extracted from the Humanitarian Data Exchange (HDX) website. This dataset provides an outline of camps of Rohingya refugees in Cox's Bazar, Bangladesh. The only file you need to reproduce this Quick-Start example is the image file *.../image/HDX_BGD_camps_thumbnail.jpg* (feel free to use any another PNG or JPG image file of your choice).


**Step 1: Create a new project and add a thumbnail**

To begin, open the Metadata Editor link and log in with your username and password. The "My projects" page will be displayed, showing all projects you have previously created and those that have been shared with you by others, if any. If you are using the application for the first time and no project has been shared with you by other users of the Metadata Editor, the project list will be empty. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_project_page.png)

Click on "CREATE NEW PROJECT" and select "Geospatial" when prompted to indicate the type of resource you will be documenting.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_document_create_project_types.png)
  
A new project page will open in a new tab.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_new_project_home.png)

We will use the JPG file *HDX_BGD_camps_thumbnail.jpg* as a thumbnail (which will be displayed in the Metadata Editor and in the NADA catalog if the metadata is published in NADA). Click on the edit button in the screenshot image, and select the image file when prompted. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_edit_thumbnail.png)

Geographic datasets are of two main types: *raster data*, and *vector data*. The same metadata standard is used for documenting all types of geographic datasets, but different templates have been developed for raster and vector data. In this example, we will use the template GEOSPATIAL VECTOR DATASET 1.0 (default template).


**Step 2: Enter metadata**

On the left navigation tree, select "Metadata information / Information on metadata" to enter optional elements used to capture information on who documented the publication and when. Enter your name, and the date in ISO format (YYYY-MM-DD). Then click on SAVE.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_metadata_information_save.png)

You can now start entering the metadata related to the geographic dataset itself. In the navigation tree, first select "Description / Introduction" and enter the required **Primary ID** (a unique identifier of your choice, e.g., JD_GEO_001; if you want to publish the document in a NADA catalog, make sure that this same identifier is not used by another user or for another image). 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_identifiers.png)

Then proceed with the other sections in the navigation tree and fill out the following elements using the following information provided in the World Bank Flickr album:
- ***Title:*** Market near Ramallah’s main mosque
- ***ID:*** Hoel_121012_DSC_3684
- ***Description:*** Tomato stand in market near Ramallah’s main mosque
- ***Photographer:*** Arne Hoel / World Bank
- ***Taken on:*** October 12, 2012 (2012-10-12 in ISO format)
- ***Tags:*** Middle East; Private Sector Development; West Bank & Gaza; market; Food; Tomato
- ***Resource type:*** Digital photo
- ***Format:*** JPG
- ***License:*** CC BY-NC-ND 2.0 (URL: https://creativecommons.org/licenses/by-nc-nd/2.0/)

This information can be entered in the Metadata Editor as follows:

| From World Bank           | In the metadata template                             | 
| ------------------------- | -----------------------------------------------------| 
| Resource type             | DCMI / Image description / Resource type             |
| Taken on                  | DCMI / Image description / Date                      |
| Title                     | DCMI / Image description / Title                     | 
| Description               | DCMI / Image description / Caption                   |
| Format                    | DCMI / Image description / Format                    |
| Tags                      | DCMI / Image description / Keywords (keyword)        |
| (derived from title)      | DCMI / Country                                       |
| Photographer (name)       | DCMI / Authors and rights / Creator                  | 
| Photographer (affiliation)| DCMI / Authors and rights / Publisher                | 
| License                   | License / License (name and URL)                     | 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_metadata.png)


**Step 3: Add information on related resources**

Once you have entered the metadata, you can finalize the documentation of the indicator by documenting and attaching external resources. External resources include all materials you want to make accessible to users when you publish the indicator in a catalog. In this example, we will add one external resource: the link to the Flickr album. 

To create external resources, click on "External resources" in the navigation tree and then click on "Create resource". Select the resource type ("Web Site"), give it a short title *(World Bank Flickr Album)*, and enter the URL *(https://www.flickr.com/photos/worldbank/14131666634/in/album-72157626025379650)*. Then click "SAVE." You will now have two external resources listed.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_external_resource_flickr.png)


**Step 4: Export and publish metadata**

In the project page, a menu of options will be available to you.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_open_actions_menu.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_actions_menu.png)

**Export package (ZIP)**

This option will allow you to generate a ZIP file containing all metadata and resources related to the project. This package can be shared with others, who can import it in their own Metadata Editor.

**Export JSON**

Export metadata as a JSON file. 

**Export RDF/XML** and **Export RDF/XML**

These options allow you to export the metadata related to external resources in JSON or XML format.

**PDF documentation**

A PDF version of the metadata can be automatically created. Select PDF documentation then click on GENERATE PDF. When the PDF is generated, click on DOWNLOAD PDF. You will obtain a bookmarked PDF file with all entered metadata.

**Publish to NADA**

If you have a NADA catalog and the credentials to publish content in it, you can also "Publish to NADA". Select a configured NADA catalog, select the options as shown in the screenshot below, and click PUBLISH.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_publish_to_NADA.png)

The image will now be listed and made discoverable in the NADA catalog, with a link to the Flickr Album. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_geographic_indicator_in_NADA.png)

