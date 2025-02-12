# Quick-start: Microdata

In this Quick Start example, we will document a survey dataset (microdata) using the DDI Codebook metadata standard. The example only illustrates a few core features of the Metadata Editor. For a complete overview of the software's features, please refer to the "Microdata" section in the "Documenting Data" chapter.

The dataset we will document is a synthetic dataset representing a sample household survey for a fictional country. The dataset, along with its related resources, can be found in the "Demo/Microdata" folder in the GitHub repository. Download and save the content of this folder in a local folder of your choice. The materials provided include:

- Stata (version 17) data files. All variables and values have been labeled in the Stata files:
   - *training_survey_data_hh.dta* (household-level data file, in Stata 17 format, with 47 variables and 7,975 observations). 
   - *training_survey_data_ind.dta* (individual-level data file, in Stata 17 format, with 26 variables and 30,986 observations). 
- Survey questionnaire and survey documentation, in the MS-Excel file *synthetic_survey_questionnaire_info.xlsx*. This file contains:
   - A simplified survey questionnaire (in sheets "Household form EN" for variables collected at the household level, and "Individual form EN" for variables collected at the individual level.)
   - A simplified technical survey report, with information on the sampling design (in sheet "Survey info")
- Other: *survey_logo.JPG* (a logo for the survey, in JPG format)

To begin, log in with your username and password, and navigate to the "My projects" page of the Metadata Editor. This page displays all the projects you have created and those that have been shared with you by others. If you are using the application for the first time, the project list will be empty. 

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/8881df36-49cb-4b47-8acd-9f0ba8237727)

Click on "Create project" and select "Microdata" when prompted.

![image](https://github.com/ihsn/editor/assets/35276300/f52bcdc3-c677-4a72-90f4-a3d1da3b65ac)
  
A new project page will open in a new tab.

You can change the image that will be used as a thumbnail for the project (optional). The demo materials contain an image file named *survey_logo.jpg*. Click on the edit button and select this file (or another jpg file of your choice)".

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/3dbbf6db-9e49-419a-b9a4-0ae1f7fec152)

We will use the default metadata template to document the dataset, so there is no need to switch template. You are now ready to start documenting the dataset.

In the section "Document description / Metadata preparation", enter information on the metadata. This information is optional. Enter your name and the date the metadata was created, then SAVE.

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/c805cf14-5b59-4d51-9caf-ab10174de30e)


In the section "Study description / Identification", enter the relevant information on the survey. First, enter the title of the dataset and a primary unique identifier for the dataset, e.g., "QS_MICRO_001". Then browse the navigation tree and find the most appropriate elements for each piece of information. use information found in sheet "Survey info" of the Excel file to populate other metadata elements with the information provided. All information contained in the Survey info sheet sheet should be entered in the corresponding metadata elements. The (?) icon next to each element label will display a description of the element. SAVE after you enter the metadata.

When all available "Study description" is entered, click on "Data files" in the navigation bar. On the Data files page, click "Import data", select the two Stata data files to be imported, then click "Import files".

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/cf9874ce-74ab-4089-808d-e669673fc778)

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/b6f8ebdf-56d8-4932-a32b-cd9569b6e28b)

The Editor will read and import the data files, and extract all available metadata from the files (variable list, names, variable labels, value labels). It will also generate summary statistics.

The "Data files" page will now display your two files, which will also be listed in the navigation bar.

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/85a78852-2d2c-4f25-9c2f-2224565d2265)

You can preview the data by clicking "Data", but note that the data cannot be edited in the Metadata Editor.

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/396f489b-a7c3-467d-8821-dcaa0e729faa)

You will now document the data files and the variables they contain.

First, click on the filename of a data file in the navigation tree and add a brief description of the file and SAVE. Do that for both data files. 

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/5a2f4d77-e275-479d-a39f-87c0e81e22b7)


Next, we will add or edit the variable-level information. In the navigation bar, select "Variables" in the navigation bar for one of the data files. 

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/75cc1d25-b9db-4fc0-8159-7404d3baf06f)

The page displays a list of variables for the selected file, along with multiple options to edit and complete the metadata related to the variables. On this page, you can:

- Edit the variables labels.
- Edit the value labels (for discrete/categorical variables only).
- If necessary, delete variables.
- Identify a variable as being a sample weight.
- Add metadata related to the variable (literal question, interviewer instructions, derivation and imputation, and more) in the "DOCUMENTATION" tab.
- Identify values to be considered as "missing." The system missing values in Stata or SPSS will be automatically identified as "missing." However, in some cases, one (or multiple) values may be used to represent missing values (e.g., "99" representing missing or unknown for a variable such as age).
- Set the weighting coefficient (if relevant) to be applied to generate summary statistics.
- Select the summary statistics to be included in the metadata (in tab "STATISTICS").

Note that you cannot rename variables in the Metadata Editor. This considered as a change of data. If you need to change your data (renaming variables, creating new ones, deleting observations, or editing the data themselves), you will have to do that outside the Metadata Editor and re-import the modified data files.  

Assuming that all variable labels and value labels are good as imported, browse the list of variables to check that their type has been properly detected when the data were imported. For instance, the variable "hhsize" (household size) in the file training_survey_data_hh.dta has been imported as a discrete variable. This may be fine, but let's assume you want it to be imported as a continuous variable. Change the type from "Discrete" to "Continuous."  

Now, add metadata specific to each variable. Most of the metadata at the variable level that were not extracted from the imported data files will typically be found in the survey questionnaire and the interviewer manual. The "DOCUMENTATION" tab displays the metadata for the variable(s) selected in the list of variables. Add the following information:

- Universe of the variable
- Pre-question, literal question, and post-question (for collected variables, not for derived variables)
- Derivation or imputation methods (for derived variables)

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/5100a5e8-0442-44af-90ef-e9bc5a4bd75c)

Note that when the information is the same for multiple variable, you can enter it for more than one variable by selecting multiple variables (using the Shift or Ctrl key) and entering information for the relevant element(s). For example, the three variables related to education in the individual dataset have the same universe ("Population aged 6 and above"). The three variables can be selected, and the information entered in "Universe" will be automatically applied to all three variables.

Set the "weight" variable (and also the "popweight" variable in the household-level data file) as weighting variables.

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/4c8af677-4a87-409f-9b55-bfd5319e23ee)

To display and store weighted summary statistics, you need to apply weights to the relevant variables. This can be done in the WEIGHTS tab.

![image](https://user-images.githubusercontent.com/35276300/233706439-577b3451-9470-4104-ae2d-5bd8e880a94c.png)

First, select the variables to which you want to apply a weighting coefficient (select a block of variables using the Ctrl or Shift key). Then, click on "Select weight variable" and select the weight variable to be applied (only variables that have been declared as "Is weight" will be listed in the options. For the household-level file, you may first select all variables except the quintile variables and apply the "hhweight" variable (only variables that have been tagged as weight will be listed in the selection). Next, repeat the process for the three quintile variables, but use the "popweight" variable as weight.

![image](https://github.com/mah0001/metadata-editor-docs/assets/35276300/1475d719-8b8d-4ebc-95c7-c046d87b2a09)

The summary statistics will now display both the unweighted and weighted values.

As a last step in documenting variables, browse the variables and verify that the selected summary statistics for each variable correspond to what you want to store in your metadata. Note that means or standard deviations should not be included for categorical variables.

![image](https://user-images.githubusercontent.com/35276300/234379255-45de7402-3955-40ad-b68c-d750c7f00631.png)


Once you have entered the variable-level metadata for both files, you can finalize the documentation of the dataset by documenting and attaching external resources to the survey metadata. External resources include all materials you want to make accessible to users when you publish the dataset in a catalog. This includes the microdata files, if you want to disseminate them openly or under restrictions. For our survey metadata, we will add two external resources: the Excel file that contains the questionnaire and the dataset (the two Stata files compressed as one zip file). Note that you could provide the data in more than one format, for example, you could also share a version of the files in CSV and SPSS formats for user convenience.

To create external resources, click on "External resources" in the navigation tree and then click on "Create resource". Select the file type ("questionnaire" and "microdata" for our two external resources) and give each a short title.


Provide a link to the resource or select the file you want to upload in your online catalog, then click "SAVE."

![image](https://user-images.githubusercontent.com/35276300/233708637-2432c485-6ac4-472f-a2f4-2e5f010ef195.png)


Your dataset documentation is now complete. You can export the DDI and the RDF metadata and save the full package as a project zip file. If you have a NADA catalog and the credentials, you can also publish your data and metadata in the catalog.


The dataset will be accessible and discoverable in your NADA catalog with detailed metadata, including the data dictionary.
