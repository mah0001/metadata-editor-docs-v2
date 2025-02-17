# Documenting microdata

Microdata is ...
Standard in the Metadata Editor is the DDI Codebook
For external resources, template based on Dublin Core
Export DDI JSON or XML, and other formats 
Template may include non-DDI elements
Administrative metadata, not in DDI

## Before you start:

Recommendations on preparing the data and documentation.

## Create a project

See quick start: Microdata
Template selection

## Document the dataset

Can enter metadata then import data, or start importing data (sequence does not matter)
DDI Codebook has the following sections:
- Document description
- Study description
- File description
- Variable description
- Variable groupings

  Add
  - External resources
  - Administrative metadata
  - Provenance

Project must have some information in Study description. Not required to have file and variable level metadata. If you have that, structural metadata. If you publish data, must have that.

### Document description

Metadata about the metadata. Corresponds to "Information on metadata" in other standards.
Highly recommended.

### Study description

Cataloguing and referential metadata. Standard requires at least an ID and title.
Maximize content.

### Importing data files

Click IMPORT, select files. 
Import and convert to CSV internally. 

- Python in background (Pandas)
- Format supported: ...
- Generate summary stats (unweighted)
- Imports metadata: variable names, variable labels, value labels
- Guess variable types
- Data on server ! Can be removed. Needed if weighting or change statistics. Can see size, delete.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_list_data_files.png)

**Reordering data files**


**Exporting data files**

**Deleting data files**
Remove them from the project. All related metadata will be removed.

**Removing data files from server**
Clear data. Keep all metadata, but do not store data on server. Cannot refresh statistics anymore.

**Replacing data files**
![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_refresh_replace_data_files.png)

**Refreshing summary statistics**


### File description

### View data

View, not edit. Can export. Formats: SPSS, Stata, CSV, JSON, SAS.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_view_data.png)


### Variable description

Detailed data dictionary. Some metadata imported from data files. But can add a lot. Very useful for discoverability and usability.  

- **Variable list**

Variable name, variable label, icons showing the status. 
    ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_list_frame.png)
    
Can edit variable label. Should all have one, all variables should have a different label.

**Toolbar**:
   - ***Refresh stats***
   
   - ***Change case***
     
     ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_change_case.png)

   - ***Spread metadata***
   
   - ***Delete selection***

**Status Icons**
   - Numeric [1]
   - Character [A]
   - Has categories (tooltip will tell you how many)
   - Weighted
   - Needs refreshing statistics
     
Tip: block selection

- **Variable documentation**

  ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_frame.png)

   ***Toolbar***
     - > < >> <<

   ***Settings***

   ***Statistics***

  ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_statistics.png)

   ***Weights***

  ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_weights.png)

   ***Documentation***

   ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_documentation.png)

   ***JSON***

  ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_documentation_json.png)


- **Variable categories** (value labels)
  
  When the data are imported, if they are detected as being categorical variables, the *Variable categories* will be automatically populated. If value labels are included in the data file, they will be imported. These labels can be edited in the *Variable categories* frame. Codes can also be added if necessary.
  If the categories were not detected when the data were imported, the Metadata Editor provides an option to automatically *Create categories*. This option is accessed by clicking on the icon at the top of the frame. When this icon is clicked, the application will extract a list of all codes found for the variables in the data, and create a list of categories. The labels corresponding to each category can then be added by the data curator. An icon is also provided to *Clear all* categories in the list.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_value_labels.png)

Categories can be removed from the list by clicking on the trash icon.

An option is also provided to copy/paste content in the list of value labels. This allows for example to copy code lists from an application like MS-Excel and to paste them in the *Variable categories* grid. The pasted information can either *replace* existing content of the grid (if any), or *append* content to it.  

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_value_labels_copy_paste_access.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_value_labels_copy_paste_menu.png)

- **Variabe information**

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_information.png)

   - ***Is weight***

    ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_weights.png)

   - ***Interval type***
     Continuous or discrete

   - ***Type***
     Numeric, character, fixed

   - ***Min, Max, and Decimal point***
     
   - ***Missing***
  
- Import metadata from existing file (use case: DDI from Survey Solutions; similar survey)
- Apply default

### Variable groupings

Purpose
How to

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_groups_create.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_groups_select_item.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_groups_selection.png)

### External resources
- Recommendations
- How to add
- Specific case of microdata
- Format for microdata

### Importing metadata ###

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_import_metadata_menu_access.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_import_metadata_menu.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_import_project_metadata.png)


### Spreading metadata ###

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_spread_metadata_icon.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_documenting_microdata_variable_spread_metadata.png)

### Diagnostic


### Export metadata


### Publish metadata ###



