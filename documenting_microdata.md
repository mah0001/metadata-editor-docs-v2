# Documenting microdata

## Defining microdata ##

When surveys or censuses are conducted, or when administrative data are recorded, information is collected on each unit of observation. The unit of observation can be a person, a household, a firm, an agricultural holding, a facility, or other. **Microdata** are the data files resulting from these data collection activities, which contain the **unit-level** information (as opposed to aggregated data in the form of counts, means, or other). Information on each unit is stored in variables, which can be of different types (e.g. numeric or character variables, with discrete or continuous values). These variables may contain data reported by the respondent (e.g., the marital status of a person), obtained by observation or measurement (e.g., the GPS location of a dwelling or other sensor), or generated by calculation, recoding or derivation (e.g., the sample weight in a survey).

For efficiency reasons, variables are usually stored in numeric format (i.e. coded values), even when they contain qualitative information (coded values). For example, the sex of a respondent may be stored in a variable named ‘Q_01’, and include values 1, 2 and 9 where 1 represents “male”, 2 represents “female”, and 9 represents “unreported”. Microdata must therefore be provided at a minimum with a *data dictionary* (i.e., structural metadata) containing the variables and value labels and, for derived variables, information of the derivation process. But many other features of a micro-dataset should also be described such as the objectives and the methodology of data collection, a description of the sampling design for sample surveys, the period of data collection, the identification of the primary investigator and other contributors, the scope and geographic coverage of the data, and much more. This information will make the microdata usable and discoverable.

## Metadata standards

### DDI Codebook for documenting the dataset

The Data Documentation Initiative (DDI) metadata standard provides a structured and comprehensive list of hundreds of elements and attributes which may be used to document microdata. It is unlikely that any one study would ever require using them all, but this list provides a convenient solution to foster completeness of the information, and to generate documentation that will meet the needs of users.

The Data Documentation Initiative (DDI) metadata standard originated in the Inter-university Consortium for Political and Social Research (ICPSR), a membership-based organization with more than 500 member colleges and universities worldwide. The DDI is now the project of an alliance of North American and European institutions. Member institutions comprise many of the largest data producers and data archives in the world. The DDI standard is used by a large community of data archivists, including data librarians from academia, data managers in national statistical agencies and other official data producing agencies, and international organizations. The standard has two branches: the *DDI-Codebook* (version 2.x) and the *DDI LifeCycle* (version 3.x). These two branches serve different purposes and audiences. The DDI standard is published under the terms of the [GNU General Public License]((http://www.gnu.org/licenses) (version 3 or later).

The Metadata Editor implements the DDI-Codebook. It uses a slightly simplified version of version 2.5 of the DDI Codebook, to which a few elements are added. The Metadata Editor exports fuly-compliant DDI Codebook metadata.

The DDI Alliance developed the DDI-Codebook for organizing the content, presentation, transfer, and preservation of metadata in the social and behavioral sciences. It enables documenting microdata files in a simultaneously flexible and rigorous way. The DDI-Codebook aims to provide a straightforward means of recording and communicating all the salient characteristics of a micro-dataset. It is designed to encompass the kinds of data resulting from surveys, censuses, administrative records, experiments, direct observation and other systematic methodology for generating empirical measurements. The unit of observation can be individual persons, households, families, business establishments, transactions, countries or other subjects of scientific interest.

The DDI Alliance publishes the DDI-Codebook as an XML schema. We present in this Guide a JSON implementation of the schema, which is used in our R package NADAR and Python Library PyNADA. The NADA cataloguing application works with both the XML and the JSON version. 

The technical description of the JSON schema used for the documentation of microdata is available at https://worldbank.github.io/metadata-schemas/#tag/Microdata.

### Dublin Core for documenting external resources

For documenting external resources, a template based on the Dublin Core standard is used. See sections **General instructions** and **External resources**.


## Before you start

Before you start documenting a micro-dataset, it is highly recommended to carefuly prepare the data and the related materials.

- **Prepare your data files**
   - ***Variable and value labels***: Ensure that all variables and values are labeled (if the data are stored in Stata, SPSS, or another application that loows documentation of variables)
   - ***Direct identifiers***: Drop the direct identifiers from the dataset (names, phone number of respondents, addresses, social security numbers, etc) if you plan to share the data. This information should be kept confidential, unless the respondents provided an explicit consent to have their personal data published.
   - ***Unique identifiers and relationships***: Check that each observation in each data file has one or a combination of variables that provide a unique identifier for each observation. Ensure that there are no duplicated identifiers of observations in any data file. If your dataset is composed of multiple related data files, check that the files can be merged without any issue. For example, if you have data files at the household and individual levels, make sure all households have at least one corresponding individual, and that each individual belongs to one and only one household.
   - ***Missing values***: Use system missing values (instead of values like '999') for indicating missing values. 
   - ***Work variables***: Drop all temporary or working variables that do not need to be part of the data.  
   - ***Weighting***: Include the sampling weight variables in all data files where they apply. 
   - ***File names***: Name your data (and other) files using names that make them easy to understand.
   - ***Format data files***: If necessary, export your data files to a format supported by the Metadata Editor.

  - **Prepare the related materials to be included as external resources**
     - Have a copy of the questionnaire or data collection form in electronic format. Include the file in both the original format and in a PDF version. If the survey was conducted using computer-assisted interviews using a software like Survey Solutions or CsPro, generate a PDF copy of the electronic form (Survey Solutions provide an otion to generate such a file).
     - Collect an electronic copy of all other relevant documents, such interviewer manuals, technical documentation on sampling, survey technical and analytical reports, presentations of results, press releases, etc. For documents in proprietary format, generate a PDF copy.
     - Collect other digital materials related to the dataset, such as data editing scripts, photos and videos, etc.

## Create a project

The first step in documenting a dataset is to create a new project. You do that by clicking on CREATE NEW PROJECT in the *My projects* page. Select *Microdata* as data type. This will open a new, untitled *project home page*. 

In that page, select the Template you want to use to document the dataset. A default template is proposed; no action is needed if you want to use the default template. Otherwise, switch to another template by clicking on *Switch template* in the **Templates** frame. Note that you can at any time change the template used for the documentation of a project. The selected template will determine what you see in the navigation tree and in the metadata entry pages, but switching from one template to another will not impact the metadata that has already been entered; no information will be deleted from the metadata.


## Document the dataset

Once a project has been created, you can start entering metadata and subsequently import the data files (assuming you want to include file and variable-level documentation, which is not mandatory), or you can first import the data files then add metadata. The sequence in which you document the dataset does not matter. 

Refer to the **General instructions** for instructions on sections common to all data types.

The DDI Codebook metadata standard used to document microdata has the following sections (*containers*), which will be found in any template designed based on that standard:
- **Document description:** This section contains metadata on the metadata (to capture information on who documented the dataset, when, etc.)
- **Study description:** This section contains cataloguing and referential metadata that describe the study (survey, census, administrative recording system), with information like the title, geographic and temporal coverage, producers and sponsors, and many more.
- **File description:** This section provides a brief description of each data file.
- **Variable description:** The section contains the documentation of each variable, with elements like variable name and label, value labels, literal questions and interviwer instructions, universe, summary statistics, and more.
- **Variable groups:** This optional section provides a way to organize variables into groups other than the data files, e.g., grouping of variables by theme. Variable grouping is intended to increase the convenience to users, and possibly the online discoverability of data (if useful group descriptions are provided).

![image](img/ME_UG_v1-0-0_documenting_microdata_DDI_containers.png)

The container **Tags** is not part of the DDI Codebook standard. It is a container that has been added to all metadata standards used by the Metadata Editor. Refer to **General instructions** for information on tags.


### Document description

The **Document description** section of the navigation tree contains elements intended to document the metadata being generated ("metadata about the metadata"). In the DDI jargon, the *document* is the DDI-compliant metadata file (XML or JSON) that contains the structured metadata related to the dataset. This section corresponds to the section **Information on metadata** in other standards. 

All content in this section is optional; it is however good and recommended practice to document the metadata as precisely as possible. This information will not be useful to data users, but it will be to catalog administrators. When metadata is shared across catalogs (or automatically harvested from DDI-compliant data catalogs), the information entered in the **Document description** provides transparency and clarity on the origin of the metadata.


### Study description

The **Study description** section of the DDI Codebook metadata standard contains the **cataloguing and referential metadata**. Two metadata elements are required in this container: the *primary unique identifier* of the dataset, and its *title*. Other elements are optional, unless they have been set as *required* in a custom-defined template.

The metadata entered for this section should be as comprehensive as possible. You enter metadata by selecting a section in the nagivation tree, and entering the information in the metadata entry page.

Note that all dates should preferably be entered in ISO format (YYYY-MM-DD or YYYY-MM or YYYY).

Refer to **General instructions** for information on importing metadata from an existing project, and on copy/pasting content in fields that allow it.

By default, all content entered in the metadata entry page will consist of plain text (which will be saved in XML or JSON format). A few fields may allow entering formatted content (markdown, HTML, or LaTex formulas); which fields allow for such formating is determined in the template design.


### Data files

The **Data files** section of the DDI Metadata Editor is where ***structural metadata*** will be captured, including file-level and variable-level information. 

***Importing data files***

Typically, the core of structural metadata will be automatically generated by importing the data files. When no data file is available to be imported, this section will be left empty, or information can be entered manually, which may be a tedious process.

To import data files, select *Data files* in the navigation tree, and click IMPORT in the *Data files* page. Select the file(s) to be imported. The following formats are currently supported: Stata (.dta), SPSS (.sav), and CSV. The Metadata Editor runs Python in the background (library Pandas). It will read the data files, and convert them to CSV for internal use. The application will make a best guess for the type of each variable (continuous or categorical), extract variable names and labels, extract value labels, and generate (unweighted) summary statistics for all variables. The import process will thus result in a data dictionary for each data file.

The imported data files will now be listed in the navigation tree. Summary information on the imported data files is displayed in the *Data files* page. 

![image](img/ME_UG_v1-0-0_documenting_microdata_list_data_files.png)

IMPORTANT: The CSV version of the data will be stored on the server that hosts the Metadata Editor. **All collaborators on your project will be able to see and download the data.** If the data are confidential and sensitive, they may be removed from the server at any time. See ***Removing data files from server*** below.  

**Reordering data files**

If the order in which the files appear in the *Data files* page needs to be modified, use the handle icons to move the files up or down (drag and drop). This allows you to ensure that the metadata on data files will be displayed in the right order.

**Exporting data files**

At any time, you may export the imported data files, to any of the supported format (currently, Stata, SPSS, and CSV). Typically, you will want to export the data files AFTER editing the metadata (variable and value labels) to ensure full consistency between the data and the metadata.

**Deleting data files**

Data files can be **deleted** from the project. When you delete a data file, all related metadata will be removed, and the data for the deleted file will also be removed from the server. 

**Removing data files from server**

If you want to preserve the imported metadata on a data file but remove the data from the server, use the **Clear data** option provided in the *Data files* page. Note that after removing the data from the server, you will not be able to update the summary statistics anymore. If you plan to edit the value labels, or apply weights to generate weighted summary statistics, do that BEFORE you clear the data files from the server. And if you want to ensure that no collaborator has access to the data, clear the data files BEFORE sharing the project or adding it to a collection.

**Replacing data files**

You can replace a data file by selecting the option **Replace file** in the option menu for a data file in the *Data files* page. You can only replace a data file with a data file that has the exact same structure (same variables, in the same order). The application will replace the data, but leave the metadata already entered in the Metadata Editor untouched. Replacing a data file is thus a solution to "refresh the data" (and summary statistics) without losing updated metadata.

![image](img/ME_UG_v1-0-0_documenting_microdata_refresh_replace_data_files.png)

**Refreshing summary statistics**

Some actions on data files (modifying *Categories description* or applying weighting coefficients) will require that the summary statistics be updated. The Metadata Editor does not automatically update statistics each time a change is made. Instead, it will add visual clues (red icons) that the data does not fully correspond to the metadata anymore, and call for a refreshing of summary statistics. The *Refresh summary statistics* in the option menu next to the data file description (in the *Data files* page) serves this purpose. Another option to refresh statistics is to click on the **Refresh stats** icon in the *Variable list* frame of the Variable page (see *Refresh statistics* below). 

**File description** 

Clicking on a file name in the navigation tree will open the *File description* page where the information on the data file can be entered.

![image](img/ME_UG_v1-0-0_documenting_microdata_data_file_description.png)


### Variables

The variable description section of the DDI Codebook standard provides you with the possibility to create a very rich data dictionary. While some of the variable-level metadata will be imported from the data files, the DDI Codebook contains many elements that can enrich the data dictionary. This additional information is very useful both for discoverability and for increased usability of the data. 

After importing a data file in the Metadata Editor, you can access information on the variables it contains by clicking on *Variables* below the file name in the navigation tree. This will open the *Variables* page, which contains four frames: 
- ***Variables:*** This frame provides the list of variables in the data file, with their name, label, and status icons.
- ***Variable categories:*** This frame describes the categories (value labels) for a categorical variable selected in the list of variables.
- ***Variable description:*** This frame contains information on the status and type of the variable selected in the variable list, on its range, and on missing values.
- ***Statistics, weights, documentation, and json:*** This frame is used to edit the documentation of the selected variable(s), select the summary statistics to be included in the metadata, and apply sampling weights if needed.

These four frames are described in detail below.

- **Variable list**

The variable list displays the list of variables in the selected data file, with their name and label. A search bar is provided to locate variables of interest (keyword search on variable name and label).

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_list_frame.png)

   - The variable labels can be edited (double click on a label to edit it). All variables should have a specific label.
   - The variable names cannot be edited.
   - A set of icons provides information on the status of each variable, as follows:

      ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_list_icons.png)

The icons shown on top of the variable list perform the following actions on variables:
![image](img/ME_UG_v1-0-0_documenting_microdata_buttons_variable_list.png)

   - ***Refresh statistics:*** Instructs the Metadata Editor to re-read the data files and update the summary statistics for all variables. You will want to refresh the summary statistics after performing actions like applying sample weights or modifying the value labels (categories) of some variables. Note that this will not be possible if you have cleared the data from the server.
   
   - ***Change case:*** This allows you to change the case of the variable names and/or variable labels (changing them to uppercase, lowercase, or sentence case). Note that changing variable names is not always a good idea; some software like Stata or R are case sensitive; changing the case of a variable name is equivalent to changing the variable name, which means that some scripts written to run on the original data will not run anymore on data with renamed variables.
     
     ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_change_case.png)

   - ***Spread metadata:*** In many micro-datasets, a small number of variables will be common to all data files. For example, in a sample household survey, the household identifier, and the variables that indicate the geographic location of the household, may be repeated in all files. In such case, you can document the variables in one data file, select these common variables, and "spread metadata" to automatically apply the metadata to variables with the same name in other data files. 
   
   - ***Delete selection:*** The Metadata Editor is not a data editor; data files cannot be modified, with the exception that variables can be deleted from a data file. This option is provided to drop variables like temporary variables or direct identifiers that may have been accidentally left in the data files. To drop variables, select them in the variable list (using the Shift and Ctrl key as useful to select multiple variables), then click on the **Delete selection** icon. 

- **Variable categories** (value labels)
  
  When the data are imported, the Metadata Editor makes a best guess about their type. If a variable is identified as categorical, the *Variable categories* will be automatically populated with codes and value labels. These codes and labels can be edited in the *Variable categories* frame. Codes can also be added if necessary.

  The *Variable categories* frame contains the following icon toolbar:

![image](img/ME_UG_v1-0-0_documenting_microdata_toolbar_categories.png)

  If a categorical variable was not identified as such when the data were imported, the Metadata Editor provides an option to automatically *Create categories*. This option is accessed by clicking on the **Create categories** icon at the top of the frame. The application will then extract a list of codes found for the variables in the data, and pre-populate the list of categories with the codes. The labels corresponding to each category can then be added by the data curator. An option (**Clear all** icon) is also provided to remove all content from the list of categories.

![image](img/ME_UG_v1-0-0_documenting_microdata_value_labels.png)

   A category can be removed from the list by clicking on the trash icon.

   An option is also provided to copy/paste content in the list of value labels. This allows for example to copy code lists from an application like MS-Excel and to paste them in the *Variable categories* grid. The pasted information can either *replace* existing content of the grid (if any), or be *appended* to it.  

![image](img/ME_UG_v1-0-0_documenting_microdata_value_labels_copy_paste_access.png)

![image](img/ME_UG_v1-0-0_documenting_microdata_value_labels_copy_paste_menu.png)


- **Variable information**

The **Variable information** frame provides options to tag a variable as being a sample weight, to edit the type of the variable, the range, and the format of the data it contains, and to inform the application of values to be treated as missing values.   
![image](img/ME_UG_v1-0-0_documenting_microdata_variable_information.png)

   - ***Is weight***

      The **Is weigh** toggle is used to tag variables that are sample weights, if any.  
    ![image](img/ME_UG_v1-0-0_documenting_microdata_weights.png)

   - ***Interval type***
      For numeric variables, the *interval type* can be set to *Continuous* or *Discrete*. This will impact how the data are documented and what summary statistics are produced (frequencies will not be calculated for continuous variables; variable categories will only be created for discrete variables). When data are imported, the application makes a best guess about the interval type. the data curator should browse through all variables to ensure the interval type has been properly set. 

   - ***Type***
     This option informs the system of the format type of the variable, with options *numeric*, *character* (string variables), and *fixed*.

   - ***Min, Max, and Decimal point***
      A range of valid values can be entered in this element; values outside the range will trigger a validation error.   
     
   - ***Missing***
      The proper use of data requires proper treatment of missing values. The application (and data users) needs to know what values in the data files are to be considered as *missing*. When data are imported from Stata or SPSS, if the system missing values were used in the origial files, the missing values will be showns as *. But other values may represent missing values. In some survey datasets, the code 99 for example may be used to represent "unknown or unreported age*. When such values (other than system-missing) are used, they must be indicated as representing missing data, otherwise the summary statistics will be incorrect (e.g., 99 would be treated as a valid age eventhough it means "unreported"). One or multiple values representing *missing* can be entered for the variable. 
  

- **Variable documentation**

   The last frame of the Variable page is one where most of the additional metadata related to variables will be entered.
  
  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_frame.png)

   ***Header bar***
   The header bar of the frame shows the name and label of the variable selected in the Variable list. It also shows four icons, which allow you browse variables without having to select them in the Variable list. 

  ![image](img/ME_UG_v1-0-0_documenting_microdata_navigate_variables.png)
  
   ***Statistics***

   The STATISTICS tab shows the summary statistics generated by the application when the data are imported (or when the statistics are refreshed). If you have applied weighting coefficients (see **Weights** below), the summary statistics will include both weighted and unweighted statistics. Otherwise, the statistics are unweighted. Keep in mind to properly document values that should be interpreted as missing values, to ensure that statistics like means and standard deviations are valid (see **Missing** above).

   The option is offered in this tab to select the summary statistics to be included in the metadata. Uncheck the statistics that you do not want to store in the metadata. For example, you do not want to keep statistics like mean or standard deviation for categorical variables. Only keep statistics that are meaningful. Note that you may select a group of variables in the *Variable list* and apply a selection to all selected variables at once.

  Note that summary statistics that will be stored in the metadata are statistics for each variable taken independently. No cross tabulation is possible.
  
  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_statistics.png)

   ***Weights***

  If the dataset is a sample survey for which sample weights have been calculated, you should tag all variables that are sample weights (see **Weights** above). Variables that have been tagged as being weights can then be used to generate weighted statistics in tab STATISTICS. To do that, select the variables for which you want to generate weighted statistics (this should not include variables like unique identifiers or the weighting variables themselves). Use the Shift or Ctrl keys to select multiple variables in the list. Then click on *select weight variable*. The list of variables in the data file that have been tagged as weights will be displayed. Select the one to be used as weight, then close the selection popup menu. A green dot will appear next to the tab name, to indicate that a weight has been applied to the variable. The variable used as weight will be shown in the tab. An option to *remove* or *change* the weight is provided. A red icon will appear in the variable list to indicate that a change has been applied to the variable that requires refreshing the summary statistics. After you refresh the summary statistics, the STATISTICS tab will display the weighted values.  

  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_weights.png)

   ***Documentation***

   The DOCUMENTATION tab is where you will enter variable-level metadata that will enrich the data dictionary. In this page, you will find a form allowing you to enter information on each variable like literal questions (for surveys), universe, concepts, interviewers' instructions, methodology, derivation and imputation, and more.
 
  A **Settings** menu allows you to select the metadata elements to be used to document variables. This selection will reduce the length of the form used to enter the metadata. The only purpose of this selection is to nake the metadata entry page shorter and more convenient to use, by focusing only on the metadata elements for which content may be provided.
  
  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_metadata_settings.png)

  Note that you may select multiple variables in the *Variable list* (using the Shift or Ctrl key) and paste content in one of these metadata elements. It will then be pasted in the metadata for all selected variables. The existing metadata for other fields will be left unchanged.
  
  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_documentation.png)

   ***JSON***

   This last tab is only intended to display a JSON version of the variable metadata.
  
  ![image](img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_json.png)


**View data**

The Metadata Editor allows you to view the content of the data files, by clicking on "Data" under the data file name in the navigation tree. You can view and export the data from this page, but you cannot edit the data. The Metadata Editor is not a data editor; changes to the data files must be made outside the Metadata Editor.

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_view_data.png)


### Variable groupings

Variables in a dataset are automatically grouped by data file. But for the convenience of users, they can also be grouped based on other criteria, e.g., by theme. These groupings will not alter the data structure in any way; variable groupings are strictly virtual. In this virtual grouping system:
- A variable can belong to more than a group
- Not all variables need to belong to a group
- A group can include variables from multiple files

Variable groups can be very useful for data discoverability, if variables are grouped by theme and if variable groups are defined. For example, a group of variables containing variables *age in month*, *sex*, *weight in grams*, and *height in cm* could be created and named "Anthropometric measures*, with a description informing users that these variables could be used to generate indicators like percentage of children stunting or wasting. This metadata, when indexed in data catalog, will improve the discoverability of the data by adding useful semantic content to the description of variables.

To group variables:
- Create a group (or subgroup) and give it a name.
- Select the variables (from any of the imported data files) to be included.
- Add a description of the group.
   
![image](img/ME_UG_v1-0-0_documenting_microdata_variable_groups_create.png)

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_groups_selection.png)

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_groups_select_item.png)


### Provenance ###

The **Provenance** container is used to document how, from where, and when the dataset was acquired. It is used to ensure traceability. See section "Documenting - General instructions" for more information.


### External resources

External resources are all materials (and links) that relate to the dataset. This includes documents and reports, scripts, photos and videos, data files, and any other resource available in digital format. These materials and links are added to the documentation of a dataset in the External resources container. Click on **External resources** in the navigation tree, then on CREATE RESOURCE. Enter the relevant information on the resource (at least a title), then provide either a filename (the file will then be uploaded on the server that hosts the Metadata Editor) or a URL to the resource.

External resources that have already been created for another project can also be imported. To do that, they must first be exported as JSON or RDF from the other project. The click on IMPORT in the External resources page, and select the file. 

External resources will be part of the project ZIP package (when the ZIP package is generated - See the main menu). 

See also section "Documentation - General instructions".


### Importing metadata ###

In the main menu, an option is provided to **Import project metadata**. This allows you to import the metadata exported from another project (DDI/XML or JSON file exported from another project of type *microdata*). This option will be particularly useful when you have dataset that belong to a same series that share common study description or data dictionary. For example, if a country conducts a monthly labor force survey using the same questionnaire over time, most of the metadata will be common to all instances of the survey. Only a few fields will need to be edited (temporal coverage, summary statistics, and a few others). In such case, the most effective way to document a new instance of the survey is to load the dataset for the latest survey, apply metadata from the previous instance, and edit the few metadata elements that need to be updated.

This option will also be used to import metadata compliant with the DDI codebook that may have been generated using another tool. For example, is a survey was conducted by CAPI interview (using tablets) using the Survey Solutions CAPI application, a DDI containing the literal questions, universe, interviewers instructions (stored in the CAPI questionnaire) can be generated. This information can be imported in the Metadata Editor, avoiding the tedious process of copy/pasting this information.

![image](img/ME_UG_v1-0-0_documenting_microdata_import_metadata_menu_access.png)

![image](img/ME_UG_v1-0-0_documenting_microdata_import_metadata_menu.png)

The components of the metadata to be imported can be selected. 

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_import_project_metadata.png)


### Spreading metadata ###

Spreading metadata consists of copying the metadata for one or multiple variables selected in the variable list, then clicking on the **Spread metadata** icon. The metadata entered for the selected variables will automatically be applied to the variables that have the same name, in the other data files. The metadata fields to be spread can be selected.

![image](img/ME_UG_v1-0-0_documenting_microdata_spread_metadata_icon.png)

![image](img/ME_UG_v1-0-0_documenting_microdata_variable_spread_metadata.png)




