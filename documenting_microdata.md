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

- Python in background (Pandas)
- Format supported: ...
- Generate summary stats (unweighted)
- Imports metadata: variable names, variable labels, value labels
- Guess variable types
- Data on server ! Can be removed. Needed if weighting or change statistics. Can see size, delete.

ME_UG_v1-0-0_documenting_microdata_list_data_files.png

**Reordering data files**


**Exporting data files**

**Deleting data files**
Remove them from the project. All related metadata will be removed.

**Removing data files from server**
Clear data. Keep all metadata, but do not store data on server. Cannot refresh statistics anymore.

**Replacing data files**
ME_UG_v1-0-0_documenting_microdata_refresh_replace_data_files.png

**Refreshing summary statistics**


### File description

### Variable description

Detailed data dictionary. Some metadata imported from data files. But can add a lot. Very useful for discoverability and usability.

- Check type
- Labels: recommendations. Tip: block selection
- Missing values
- Is weight
- Apply weights
- Summary stats selection
      - STATISTICS
- Variable metadata (select fields; block selection ; spread metadata)
     - DOCUMENTATION
- Import metadata from existing file (use case: DDI from Survey Solutions; similar survey)
- Apply default
- Value labels: Generate categories from statistics
- Value labels: copy/paste

### Variable groupings

Purpose
How to

### External resources
- Recommendations
- How to add
- Specific case of microdata
- Format for microdata

### Importing metadata ###


### Spreading metadata ###


### Diagnostic


### Export metadata

