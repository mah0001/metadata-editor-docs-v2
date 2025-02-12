# Quick-start: Microdata

In this example, we will document a survey dataset (microdata) using the DDI Codebook metadata standard. The example is only intended to illustrate a few core features of the Metadata Editor. For a complete overview of the software's features, please refer to the "Microdata" section in the "Documenting Data" chapter.

The dataset we will document is a synthetic dataset representing a sample household survey for a fictional country. The files needed to reproduce the example are provided in a folder named quick_start_files/microdata. Download and save the content of this folder in a local folder of your choice. The materials provided include:

- Two data files in Stata 17 format. All variables and values have been labeled in the Stata files. 
   - *WLD_2023_SYNTH-SVY-HLD-EN_v01_M.dta* (household-level data file containing 49 variables and 8,000 observations). 
   - *WLD_2023_SYNTH-SVY-IND-EN_v01_M.dta* (individual-level data file containing 27 variables and 32,396 observations). 
- Survey questionnaire and survey documentation, in MS-Excel format.
   - A simplified survey questionnaire (file *synthetic_survey_questionnaire.xlsx*, with sheets "Household form EN" for variables collected at the household level, and "Individual form EN" for variables collected at the individual level.)
   - A simplified technical report, with information on the sampling design (file *synthetic_survey_info.xlsx*, sheet "Survey info")
- Other: *synthetic_data_logo.jpg* (a logo for the survey, in JPG format)

**Step 1: Create a new project and add a thumbnail**

To begin, open the Metadata Editor link and log in with your username and password. The "My projects" page will be displayed, showing all projects you have previously created and those that have been shared with you by others, if any. If you are using the application for the first time and no project has been shared with you by other users of the Metadata Editor, the project list will be empty. Otherwise, the existing projects will be listed. In the screenshot below, we see that one project was already created.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_project_list_start.png)

Click on "CREATE NEW PROJECT" and select "Microdata" when prompted to indicate the type of resource you will be documenting.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_document_create_project_types.png)
  
A new project page will open in a new tab.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_new_project_home.png)

You can change the image that will be used as a thumbnail for the project (optional). The demo materials contain an image file named *synthetic_data_logo.jpg*. Click on the edit button and select this file (or another jpg file of your choice)".

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_edit_thumbnail.png)

We will use the default metadata template to document the dataset, so there is no need to switch template. You are now ready to start documenting the dataset.

**Step 2: Add information on metasdata production and document the survey itself (section Study Description)**

In the section "Document description / Metadata preparation", enter information on the metadata. This information is optional. Enter your name and the date the metadata was created, then click SAVE.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_document_description_save.png)

You can now start entering the metadata related to the survey itself in the "Study Description" section. You will find the relevant information in the Excel file *synthetic_survey_info.xlsx*. In the navigation tree, first select "Study description / Identification", enter the relevant information on the survey. First, enter the **title** of the dataset and enter the required primary ID (a unique identifier of your choice, e.g., JD_MICRO_001; if you want to publish the survey in a NADA catalog, make sure that this same identifier is not used by another user or for another entry in NADA). 

Then browse the navigation tree and find the most appropriate elements for each piece of information contained in the Excel file; populate other sections of the metadata accordingly. All information contained in the Survey info sheet sheet should be captured. The (?) icon next to each element label will display a description of the element. Click SAVE periodically or after you enter the metadata.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_study_description_save.png)

The metadata elements in the template maps to the content of the Excel file as follows: 
| In Excel file             | In the metadata template                        | 
| ------------------------- | ----------------------------------------------- | 
| Title                     | Identification / Title                          | 
| Acronym                   | Identification / Alternate title                | 
| Country / code            | Universe and geographic coverage / Country      | 
| Producer                  | Producers and sponsors / Primary producer       | 
| Funding                   | Producers and sponsors / Funding agencies       | 
| Dates of data collection  | Data collection / Dates of data collection      | 
| Abstract                  | Overview / Abstract                             | 
| Series                    | Identification / Series information             | 
| Universe                  | Universe and geographic coverage / Universe     | 
| Geographic coverage       | Universe and geographic coverage / Geo. coverage| 
| Topics                    | Scope / Topics (itemize the list)               | 
| Sampling                  | Sampling / Response rates                       | 
| Sample frame              | Sampling / Sample frame / Name                  | 
| Sample design             | Sampling / Sampling procedure                   | 
| Weighting                 | Sampling / Weighting                            | 
| Mode of data collection   | Data collection / Mode of data collection       | 
| Interviewer's training    | Data collection / Collector training            | 
| Fieldwork organization    | Data collection / Control operations            | 
| Data processing           | Data processing / Data processing               | 
| Standard compliance       | Quality standards / Standard compliance         | 
| Version of dataset        | Version / Version name                          | 
| Citation requirement      | Data access / Citation requirement              | 


**Step 3: Import and document the data files and variables (section Study Description)**

When all available information on "Study description" is entered, click on "Data files" in the navigation bar. On the Data files page, click "IMPORT FILES", select the two Stata data files to be imported, then click "IMPORT".

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_import_data.png)

The Editor will read and import the data files, and extract all available metadata from the files (variable list, names, variable labels, value labels). It will also generate summary statistics.

The "Data files" page will now display your two files, which will also be listed in the navigation bar.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_imported_data_files_list.png)

You can preview the data by clicking "Data", but note that the data cannot be edited in the Metadata Editor.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_view_data.png)

You can also view summary statistics for all variables by clicking on Variables below the filename in the navigation tree, and selecting tab STATISTICS.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_summary_statistics_no_weight.png)

You will now document the data files and the variables they contain.

First, click on the filename of a data file in the navigation tree and add a brief description of the file and click SAVE (you must save before moving to another page). Do that for both data files. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_data_file_description.png)


Next, we will add or edit the variable-level information. In the navigation bar, select "Variables" in the navigation bar for one of the data files. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_variable_list.png)

The page displays a list of variables for the selected file, along with multiple options to edit and complete the metadata related to the variables. On this page, you can:

- Edit the variables labels.
- Edit the value labels (for discrete/categorical variables only).
- If necessary, delete variables.
- Identify a variable as being a sample weight.
- Add metadata related to the variable (literal question, interviewer instructions, derivation and imputation, and more) in the "DOCUMENTATION" tab.
- Identify values to be considered as "missing." The system missing values in Stata or SPSS will be automatically identified as "missing." However, in some cases, one (or multiple) values may be used to represent missing values (e.g., "99" representing missing or unknown for a variable such as age).
- Set the weighting coefficient (if relevant) to be applied to generate summary statistics.
- Select the summary statistics to be included in the metadata (in tab "STATISTICS").

Refer to the section on Microdata Documentation for a description of all available options.

Note that you cannot rename variables in the Metadata Editor, as this is considered as a change of data. If you need to change your data (renaming variables, creating new ones, deleting observations, or editing the data themselves), you will have to do that outside the Metadata Editor and re-import the modified data files.  

Assuming that all variable labels and value labels are good as imported, browse the list of variables to check that their type has been properly detected when the data were imported. For instance, the variable "hhsize" (household size) in the file training_survey_data_hh.dta has been imported as a discrete variable. This may be fine, but let's assume you want it to be imported as a continuous variable. Change the type from "Discrete" to "Continuous."  

Now, we will add metadata specific to each variable. Most of the relevant metadata at the variable level (other than the metadata extracted automatically from the imported data files) will typically be found in the survey questionnaire and the interviewer manual. The "DOCUMENTATION" tab displays the metadata for the variable(s) selected in the list of variables. Add the following information:

- Universe of the variable
- Pre-question, literal question, and post-question (for collected variables, not for derived variables)
- Derivation or imputation methods (for derived variables)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_quick_start_microdata_variable_documentation.png)

Note that when the information is the same for multiple variable, you can enter it for more than one variable by selecting multiple variables (using the Shift or Ctrl key) and entering information for the relevant element(s). For example, the three variables related to education in the individual dataset have the same universe ("Population aged 6 and above"). The three variables can be selected, and the information entered in "Universe" will be automatically applied to all three variables.

Set the "weight" variable (and also the "popweight" variable in the household-level data file) as weighting variables.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/)

To display and store weighted summary statistics, you need to apply weights to the relevant variables. This can be done in the WEIGHTS tab.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/)

First, select the variables to which you want to apply a weighting coefficient (select a block of variables using the Ctrl or Shift key). Then, click on "Select weight variable" and select the weight variable to be applied (only variables that have been declared as "Is weight" will be listed in the options. For the household-level file, you may first select all variables except the quintile variables and apply the "hhweight" variable (only variables that have been tagged as weight will be listed in the selection). Next, repeat the process for the three quintile variables, but use the "popweight" variable as weight.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/)

The summary statistics will now display both the unweighted and weighted values.

As a last step in documenting variables, browse the variables and verify that the selected summary statistics for each variable correspond to what you want to store in your metadata. Note that means or standard deviations should not be included for categorical variables.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/)

**Step 4: Add information on related resources**

Once you have entered the variable-level metadata for both files, you can finalize the documentation of the dataset by documenting and attaching external resources to the survey metadata. External resources include all materials you want to make accessible to users when you publish the dataset in a catalog. This includes the microdata files, if you want to disseminate them openly or under restrictions. For our survey metadata, we will add two external resources: the Excel file that contains the questionnaire and the dataset (the two Stata files compressed as one zip file). Note that you could provide the data in more than one format, for example, you could also share a version of the files in CSV and SPSS formats for user convenience.

To create external resources, click on "External resources" in the navigation tree and then click on "Create resource". Select the file type ("questionnaire" and "microdata" for our two external resources) and give each a short title.


Provide a link to the resource or select the file you want to upload in your online catalog, then click "SAVE."

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/)


**Step 5: Export and publish metadata**

Your dataset documentation is now complete. You can export the DDI and the RDF metadata and save the full package as a project zip file. If you have a NADA catalog and the credentials, you can also publish your data and metadata in the catalog.


The dataset will be accessible and discoverable in your NADA catalog with detailed metadata, including the data dictionary.
