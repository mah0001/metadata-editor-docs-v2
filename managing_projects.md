# Managing projects

A ***project*** corresponds to a "dataset" of any type. It can correspond to a survey or census microdataset, an administrative dataset, a geographic dataset (or servive), a document, a statistical table, an indicator, a database, a video, an image, or a research project with its associated scripts. 

## The "My projects" page

Projects are listed in the *My projects* page. This page is the default page of the Metadata Editor. Other main pages are the *Collections* and *Templates* pages, only accessible to users with credentiels to manage collections and templates.  

The projects you see in the *My projects* page are the projects you have access to (as owner, editor, or viewer). The list of projects you see is thus based on your credentials. 

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_managing_projects_projects_list_page.png)

When the Metadata Editor is installed on a stand-alone personal computer, the credentials will not impact the list of projects you can see; all projects will be listed in the Projects page as you are the owner of all projects created on your PC. But when the application is installed on a server, using it will require login, and each user will have some roles and permissions and the list will be specific to the profile of the user. 

The projects in the *My projects* page can be filtered by data type, collection (if any), and ownership (which distinguishes project you created from those created by someone else but that you have been granted access to). Projects can also be searched by keyword (note that the search only looks for keywords in the title of the project, not in its full metadata). 

From the *My projects page*, you can perform the following actions:

- **Create a new project**, by clicking on the CREATE NEW PROJECT button. You will be asked to select a data type, then a new project page will open for an *untitled* project, with you as owner. You can start entering content for that project in that page. The new project will now be listed in the *My project page*.
  
- ***Import an existing project***, by clicking on the IMPORT button. You will be asked to enter the project type, and to upload a file. This file must be ZIP package created by the Metadata Editor (one of the export formats provided when a project is created). This *import* tool will be used to exchange projects across organizations that use the Metadata Editor. It is NOT intended to share projects among users of the same instance of the Metadata Editor (for that purpose, use the SHARE options).
  
- **Open an existing project**: Click on the project title to open the project page, where you can edit or view the project.

- **ACtions on a project**: Several actions can be performed on a selected project. A menu of options is provided when clicking on the Options button.

  ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_managing_projects_actions_on_project.png)

  The actions that can be taken from this menu are the following:
  - **SHARE**: To share the project with one or multiple registered users of the Metadata Editor. You will be asked to select the users, and the level of access you want to provide them with (View, Edit, Administrator). These users will then see your project in their own *My projects* page.
    
    ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_managing_projects_share_project.png)

    ![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_managing_projects_actions_on_project_list.png)
    
  - **ADD TO COLLECTION**: To add the project to a collection. When clicking on this option, a popup screen will open, asking you to select the collection(s). See section *Managing collections* for information on the purpose of adding projects to one or multiple collection(s).
    
  - **VIEW ACCESS**: This option will open a popup screen containing information on the project permissions. It will provide a list of users who have View, Edit, or Admin access to the project, and list the collections to which the project belongs. This summarizes the information on who, apart from you, can access the project. Permissions cannot be edited from this page. To change permissions for a project that you own, open the project; the project home page contains a section *Collaborators" where permissions can be edited.
      
  - **TRANSFER OWNERSHIP**: Use this option if you want to transfer the ownership of a project from yourself to another registered user of the Metadata Editor. When you transfer ownership, you will be offered the option to retain some access to the project you transferred.
    
  - **DELETE**: Use this option to delete a project on which you have admin rights.
    
  - **EXPORT JSON**: This action will generate a JSON file containing the project metadata. You will have the option to exclude metadata elements marked in the template as *private*, and to include (or not) the administrative metadata and the metadata on external resources.
    
  - **EXPORT PACKAGE (ZIP)**: Exporting the package means generating a ZIP file containing all materials (data, metadata, and related resources) associated with the project. You may use this option to generate files for archiving, or to create packages that you can share with another organization (who can then *IMPORT* the package into their own instance of the Metadata Editor.
    
  - **LOCK & VERSION** a project against editing.

  
- **Batch actions on projects**: You can select multiple projects using the check boxes next to the project titles, and apply an action to all selected project. In this version of the Metadata Editor, the only available batch action is to add the selected projects to a colection (see section on Managing collections.   

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_managing_projects_batch_action.png)


## The project "Home page"

