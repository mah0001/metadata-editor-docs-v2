# Permissions and roles

The Metadata Editor operates as a centralized metadata production and management system. It allows the collaborative creation, editing, and deletion of projects. In this context, it is essential to clearly define what each user's role and permissions are. This is defined by (i) controling who can access the Metadata Editor (who are the "members"), and (ii) defining the role of each member. The Metadata editor provides tools for defining roles, and for assigning them to members. The users and roles management system is accessible only to system administrators. It is accessed from the *Site administration* menu.

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_permission_users_menu_settings.png)

![image](https://github.com/mah0001/metadata-editor-docs-v2/blob/main/img/ME_UG_v1-0-0_permission_users_roles_button.png)

## Descriptions of pre-defined roles and permission levels

A set of pre-defined roles is provided by default in the Metadata Editor. Each role come with a specific set of permissions. The roles can be edited, and new ones can be created. When creating new roles, be aware that only one role can be assigned to a member.

The following roles are pre-defined, which apply to specific **Projects**:
- **Member**. A *member* does not have any permission. This is the default role that is assigned when a user registers on the Metadata Editor (or is automatically registered when an organization's authentication system is configured to provide access to all authenticated staff members). Members will only obtain a set of permissions when a system administrator grants them specific roles. 
- **Viewer**. The member is authorized to view the project (and export metadata), but NOT to export data or modify the project in any way. 
- **Editor**. This role allows users to have full access to create and manage projects their own projects or any projects shared with them. The role allows view only access to templates and collections. The users can view, print (PDF, HTML preview), export to JSON all available templates but cannot make any changes to the templates or create new templates. For projects, users can view all available templates and change the template used by the project. 
- **Owner**. 
- **Co-owner**. 
- **Reviewer**. 

For collections: The roles allow the user to manage collections such as create, edit, delete and add users to a collection. For adding projects to a collection, a user must have both admin/owner access to the project and admin/edit role for the collection. 

For administrative data:

NOTE: Publisher: For publishing, permissions are set not in the Metadata Editor but in the cataloguing application.

## Permission levels in API



## Defining a new role

The editor allows creating new custom roles. To create a new role, go to users under site administration and then click on the navigation link for “User Roles”. 
Who can do that? How?


## Assigning roles to users

***Assigning a role***

***Changing roles***



## Setting a default role

When an organization gives access to all staff (through corporate authentication system): ...



