# Designing templates

Data curators will rarely make use of all elements of a metadata standard when documenting a dataset. Many elements may not be relevant in the context of an organization. Typically, data curators will document datasets using metadata templates, i.e. customized subsets of metadata elements extracted from a metadata standard. 

Templates can be designed and edited using the Template Manager tool in Metadata Editor. Not all users of the Metadata Editor will have the credentials to creating and edit templates; this is a specific role that must be assigned to users. Templates should be created and maintained by an administrator of the data curation team, then made available to all data curators. 

More than one template can be developed for a given metadata standard, although it is recommended to keep their number small to maximize consistency and to minimize the burden of maintaining a collection of templates.

## Template list, and actions on templates

You access the Template Manager by clicking on TEMPLATES in the top menu of the Metadata editor. This will open a page showing all available templates by type of data. The list can be filtered by selecting a data **Type** in the left frame.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_home_page.png)

For each data type (for each metadata standard), the Template Manager provides one or multiple **core** templates which are non-editable. the core templates contain all elements of the corresponding metadata standard, with their default parameters. Typically, custom templates will be created by duplicating then editing the copy of a core template. 

The Template Manager allows the administrator of the system to select, for each data type, the template to be used by default (one default template per type, indicated by the radio button).

A set of options is available for any given template:

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_access_actions.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_list_actions.png)

The purpose of these various functions is as follows:

**DUPLICATE**

Clicking on DUPLICATE will generate an editable copy of the selected template. The duplicated template can then be fully customized, and saved under a new name.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_duplicate.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_duplicate_list.png)

**EXPORT** (and IMPORT)

Exporting the template will create a JSON copy of it, which can be saved as a file with [.json] extension. Exporting templates allows sharing them with other organizations, who can IMPORT templates in their own instance of the Metadata Editor.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_export_json.png)

Exported templates can be imported in the metadata Editor by clicking on **IMPORT TEMPLATE**.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_import.png)

**DELETE**

Delete the selected template (only available for custom templates, not for core templates).

**PREVIEW**

Preview will generate an HTML version of the template, which will open in a web browser.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_preview.png)

**TABLE**

This option will generate a tabular description of the template, which can be copy/pasted in MS-Excel if needed.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_table.png)

**PDF**

The PDF option generates a PDF version of the template. If the template contains detailed descriptions of all metadata elements, and examples of content, the PDF file may serve as a useful instruction guide for data curators.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_PDF.png)

**REVISIONS**

This option will provide a history of changes to the template since its creation.

**UUID**

This option allows template administrators to edit the unique identifier of the template. By default, a system identifier is created. This identifier can be changed to a more readable one. This will typically be done for administrative metadata templates.

## Editing a template

**Description page**

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_description page.png)

**Navigation bar**

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_navigation_bar.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_template_element_types.png)







