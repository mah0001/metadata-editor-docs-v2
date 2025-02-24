# Translation of the software and templates

## Translating the Metadata Editor software application

The Metadata Editor can be translated to other languages. To create translations, navigate to site administration and then under the “Settings” menu, click on “Translate”. 

Translations are done using a user interface as described below. The output of a translation will consist of a series of PHP files (with extension [.php]) that can be uploaded on the server where the Editor is installed. Instructions on where to save these files, and on how to activate a new language, are provided below.  

The Metadata Editor supports translation into any UTF8-encoded language, including Arabic, Chinese, German, and Russian. For right-to-left languages like Arabic, the UI must be adjusted for correct display. Translations only affect the labels, not the UI layout. 

Note:  The application allows translation from English to English. This option is used to modify the display of labels/text in the Editor interface. It allows site administrators to adapt the user interface to specific terms used in their organization. 

[image]

### Adding a new translation 

To create a new language, a new folder must be created in the `application/languages` folder. For example, to create a new translation for `Spanish`, a folder named `Spanish` must be created. 

[image]

Once the folder is created, it will be available on the translations page UI. 

[image]

Select the language and click "Edit". 

### Editing translations 

[image]

The items for which no translation is available will be displayed with a red background. Enter your translation in the box. Note that if the length of the translation is significantly longer than the text in English, the text may not display properly in the interface (when used in menus, buttons, or other locations with limited space). 

[image]

After translating a section, make sure to Save it. 

### Activate translation 

To use the translation for the Editor, the site settings page includes the option to set the language for the application.  

[image]

### Using multiple languages 

The site configurations page allows to select one language for the website. You can enable multiple languages. For example, you can have ‘English’ as the primary/default language and have the option for users to switch to ‘French’. To do this, it can be set using a configuration setting: 

Edit the file ‘application/config/config.php’ and update the language setting by editing the setting ‘supported_languages’. 

[Image]

When there is more than one language selected, a dropdown menu will be included on the site navigation. 

[Image]


## Translating the metadata templates







