# Documenting research projects and scripts

## Rationale

Documenting, cataloguing and disseminating **data** has the potential to increase the volume and diversity of data analysis. There is also much value in documenting, cataloguing and disseminating **data processing and analysis scripts**. Technological solutions such as GitHub, [Jupyter Notebooks or Jupiter Lab](https://jupyter.org/) facilitate the preservation and sharing of code, and enable collaborative work around data analysis. Coding style guides like the [Google style guides](https://google.github.io/styleguide/) and the [Guide to Reproducible Code in Ecology and Evolution](https://www.britishecologicalsociety.org/wp-content/uploads/2017/12/guide-to-reproducible-code.pdf) by the British Ecological Society, contribute to foster the usability, adaptability, and reproducibility of code. But these tools and guidelines do not fully address the issue of cataloguing and discoverability of the data processing and analysis programs and scripts. We propose --as a complement to collaboration tools and style guides-- a metadata schema to document data analysis projects and scripts. The production of structured metadata will contribute not only to discoverability, but also to the reproducibility, replicability, and auditability of data analytics. 

There are multiple reasons to make reproducibility, replicability, and auditability of data analytics a component of a data dissemination system. This will:  

-	Improve the **quality of research and analysis**. Public scrutiny enables contestability and independent quality control of the output of research and analysis; these are strong incentives for additional rigor in data analysis. 
-	Allow the **re-purposing or expansion of analysis** by the research community, thereby increasing the relevance, utility and value of both the data and of the analytical work. 
-	Strengthen the **reputation and credibility** of the analysis. 
-	Provide students and peers with rich **training materials**.  
-	In some cases, satisfy a **requirement** imposed by peer reviewed journals or financial sponsors of research activities. For example, the [Data and Policy Code of the American Economic Association](https://www.aeaweb.org/journals/policies/data-code) (accessed on June 29, 2020), states that *It is the policy of the American Economic Association to publish papers only if the data and code used in the analysis are clearly and precisely documented, and access to the data and code is clearly and precisely documented and is non-exclusive to the authors. Authors of accepted papers that contain empirical work, simulations, or experimental work must provide, prior to acceptance, information about the data, programs, and other details of the computations sufficient to permit replication, as well as information about access to data and programs.* 
-	Contribute to **assuring the fairness of policy advice and interventions** resulting from data analysis. Data analysis may be used to identify or target the beneficiaries of policies and programs, or may contribute otherwise to the design and implementation of development policies and projects. By doing so, they also contribute to identifying populations to be excluded from these interventions. Errors and biases may be introduced in analysis by accidental or intentional human errors, by the algorithms themselves, or they can result from flaws in the data. The analysis that informs such projects and policies should therefore be made auditable and contestable, i.e. documented and published. 


## The metadata standard

To make data processing and analysis scripts more discoverable and usable, we propose a metadata schema inspired by the schemas available to document datasets. The proposed schema contains two main blocks of metadata elements: the *document description* intended to document the metadata themselves (the term *document* refers to the file that will contain the metadata), and the *project description* used to document the research or analytical work and the related scripts. We also include in the schema the `tags`, `provenance`, and `additional` elements common to all schemas.  


## Preparing for the documentation

[to do]


## Documenting the research project

### Creating a new project

![image](img/ME_UG_v1-0-0_documenting_script_create_new_project.png)

![image](img/ME_UG_v1-0-0_documenting_script_create_new_project_type.png)

![image](img/ME_UG_v1-0-0_documenting_script_create_project_home_page.png)


### Metadata information

![image](img/ME_UG_v1-0-0_documenting_script_metadata_information.png)


### Project description

![image](img/ME_UG_v1-0-0_documenting_script_project_description.png)

We provide below a description of the metadata elements contained in the `Project description` section of the default metadata template provided in the Metadata Editor. Other templates may show a different selection, different labels, or present the elements in a different sequence. For each element, we provide between brackets the name (the *key*) of the element in the metadata standard. When you document a dataset, it is not expected that all these elements will be filled. Fill all required elements, all recommended elements when content can be made available, and fill as many as the other elements (the required and recommended elements will be those marked as *required* or *recommended* in the metadata standard or template).

- **`idno`** (*idno*) A unique identifier to the project. Define and use a consistent scheme to use. Avoid including spaces in the ID.  The ID number of a research project is a unique number that is used to identify a particular project. This ID number is a vital reference. A research project can be the formal cause of a survey, scripts, tables and knowledge products. Do not include spaces in the idno element. Use a system that guarantees uniqueness of the ID (DOI, own reference number).

- **`identifiers`** (*identifiers*) This repeatable element is used to enter identifiers (IDs) other than the `idno` entered in the `title_statement`. It can for example be a Digital Object Identifier (DOI). Note that the identifier entered in `idno` can (and in some cases should) be repeated here. The element `idno` does not provide a `type` parameter; repeating it in this section makes it possible to add that information. 
  - **`type`** (*type*) The type of unique ID, e.g. "DOI".
  - **`identifier`** (*identifier*) The identifier itself. 
   
- **`title`** (*title*) The title is the official name of the project as it may be stated in reports, papers or other documents. The title will in most cases be identical to the Document Title (see above). The title may correspond to the title of an academic paper, of a project impact evaluation, etc. Pay attention to capitalization in the title.
 
- **`sub_title`** (*sub_title*) Subtitle is optional and rarely used. A short subtitle for the project. Often the sub title is used to qualify the title or rephrase the title.    

- **`alternate_title`** (*alternate_title*) An alternate title of the project. This would be any alternate title that would help discover the research project. In countries with more than one official language, a translation of the title may be provided. Likewise, the translated title may simply be a translation into English from a country's own language.  

- **`translated_title`** (*translated_title*) A translated version of the title (this will be used for example when a catalog documents all entries in English, but wants to preserve the title of a project in its original language when the original language is not English).

                                       
- **`abstract`** (*abstract*) The abstract should provide a clear summary of the purposes, objectives and content of the project. An abstract can make reference to the various outputs associated with the research project. 
  Example: "Food price inflation is an important metric to inform economic policy but traditional sources of consumer prices are often produced with delay during crises and only at an aggregate level. This may poorly reflect the actual price trends in rural or poverty-stricken areas, where large populations reside in fragile situations. This data set includes food price estimates and is intended to help gain insight in price developments beyond what can be formally measured by traditional methods. The estimates are generated using a machine-learning approach that imputes ongoing subnational price surveys, often with accuracy similar to direct measurement of prices. The data set provides new opportunities to investigate local price dynamics in areas where populations are sensitive to localized price shocks and where traditional data are not available.",

- **`review_board`** (*review_board*) Information on whether and when the project was submitted, reviewed, and approved by an institutional review board (or independent ethics committee, ethical review board (ERB), research ethics board, or equivalent).


- **`output`** (*output*) This element will describe and reference all substantial/intended products of the research project, which may include publications, reports, websites, datasets, interactive applications, presentations, visualizations, and others. An output may also be referred to as a "deliverable". The `output` is a repeatable block of seven elements, used to document all output of the research project:
  - **`type`** (*type*) Type of output. The type of output relates to the media which is used to convey or communicate the intended results, findings or conclusions of the research project. This field may be controlled by a controlled vocabulary. The kind on content could be "Working paper", "Database", etc. 
  - **`title`** (*title*) Formal title of the output. Depending upon the kind of output, the title will vary in formality.
  - **`authors`** (*authors*) Authors of the output; if multiple, they will be listed in one same text field. 
  - **`description`** (*description*) Brief description of the output (NOT an abstract) 
  - **`abstract`** (*abstract*) If the output consists of a document, the abstract will be entered here. 
  - **`uri`** (*uri*) A link where the output or information on the output can be found. 
  - **`doi`*doi* (**) Digital Object Identifier (DOI) of the output, if available. 

- **`approval_process`** (*approval_process*) The *`approval_process`* is a group of six elements used to describe the formal approval process(es) (if any) that the project had to go through. This may for example include an approval by an Ethics Board to collect new data, followed by an internal review process to endorse the results.
   - **`approval_phase`** (*approval_phase*) A label that describes the approval phase.
   - **`approval_authority`** (*approval_authority*) Identification of the person(s) or organization(s) whose approval was required or sought. 
   - **`submission_date`** (*submission_date*) The date, entered in ISO 8601 format (YYYY-MM-DD), when the project (or a component of it) was submitted for approval. 
   - **`reviewer`** (*reviewer*) Identification of the reviewer(s). 
   - **`review_status`** (*review_status*) Status of approval. 
   - **`approval_date`** (*approval_date*) Date the approval was formally received, preferably entered in ISO 8601 format (YYYY-MM-DD). 

- **`project_website`** (*project_website*) URL of the project website.

- **`language`** (*language*) A block of two elements describing the language(s) of the project. At least one of the two elements must be provided for each listed language. The use of [ISO 639-2](https://www.loc.gov/standards/iso639-2/php/code_list.php) (the alpha-3 code in Codes for the representation of names of languages) is recommended.
  - **`name`** (*name*) The name of the language.
  - **`code`** (*code*) The code of the language. Numeric codes must be entered as strings. 
 
- **`production_date`** (*production_date*) The date in ISO 8601 format (YYYY-MM-DD) the project was completed (this refers to the version that is being documented and released.)


- **`version_statement`** (*version_statement*) This repeatable block of four elements is used to list and describe the successive versions of the project.
  - **`version`** (*version*) A label describing the version. For example, "Version 1.2" *[String]*
  - **`version_date`** (*version_date*) Date (in ISO 8601 format, YYYY-MM-DD) the version was released *[String]*
  - **`version_resp`** (*version_resp*) Person(s) or organization(s) responsible for this version. *[String]*
  - **`version_notes`** (*version_notes*) Additional information on the version if any; it is good practice to describe what distinguishes this version from the previous one(s). The version must be entered as a string, even when composed only of numbers. 

- **`errata`** (*errata*) This field is used to list and describe errata.
  - **`date`** (*date*) Date (in ISO 8601 format, YYYY-MM-DD) the erratum was released.
  - **`description`** (*description*) Description of the error(s) and measures taken to address it/them. 

- **`process`** (*process*) This element is used to document the life cycle of the research project, from its design and inception to its conclusion. This can include phases of fundraising, IRB, concept note review, data acquisition, analysis, publishing of a working paper, peer review, publishing in journal, presentation to conferences, publishing, evaluation, reporting to sponsors, etc. It is recommended to provide these steps in a chronological order. 
  - **`name`** (*name*) This is a header for the phase of the process. 
  - **`date_start`** (*date_start*) Date the phase started (preferably in ISO 8601 format, YYYY-MM-DD)
  - **`date_end`** (*date_end*) Date the phase ended (preferably in ISO 8601 format, YYYY-MM-DD)
  - **`description`** (*description*) A brief description of the phase. 
 
- **`authoring_entity`** (*authoring_entity*) This section will identify the person(s) and/or organization(s) in charge of the intellectual content of the research project, and specify their respective role.
  - **`name`** (*name*) Name of the person or organization responsible for the research project.
  - **`role`** (*role*) Specific role of the person or organization mentioned in `name`.  
  - **`affiliation`** (*affiliation*) Agency or organization affiliation of the author/primary investigator mentioned in `name`.
  - **`abbreviation`** (*abbreviation*) Abbreviation used to identify the agency stated under `affiliation`. 
  - **`email`** (*email*) Depending on the agency policies, a researcher may provide a personal email or an agency email to field inquires related to the project. 
  - **`author_id`** (*author_id*) A block of two elements used to provide unique identifiers of the authors, as provided by different registers of researchers. For example, this can be an ORCID number (ORCID is a non-profit organization supported by a global community of member organizations, including research institutions, publishers, sponsors, professional associations, service providers, and other stakeholders in the research ecosystem.) 
    - **`type`** (*type*) The type of ID; for example, "ORCID". 
    - **`id`** (*id*) A unique identification number/code for the authoring entity, entered as a string variable.

- **`contributors`** (*contributors*) This section is provided to record other contributors to the research project and provide recognition for the roles they provided. 
  - **`name`** (*name*) Name of the person, corporate body, or agency contributing to the intellectual content of the project (other than the PI). If a person, invert first and last name and use commas.
  - **`role`**  (*role*) Title of the person (if any) responsible for the work's substantive and intellectual content.
  - **`affiliation`** (*affiliation*) Agency or organization affiliation of the contributor.
  - **`abbreviation`** (*abbreviation*) Abbreviation used to identify the agency stated under `affiliation`. 
  - **`email`** (*email*) Depending on the agency policies, a researcher may provide a personal email or an agency email to field inquires related to the project.  
  - **`url`** (*url*) The URL that provides information on the contributor or its affiliate 

- **`sponsors`** (*sponsors*) The source(s) of funds for production of the work. If different funding agencies sponsored different stages of the production process, use the 'role' attribute to distinguish them.
  - **`name`** (*name*) Name of the funding agency/sponsor. 
  - **`abbreviation`** (*abbreviation*) Abbreviation of the funding/sponsoring agency. 
  - **`role`** (*role*) Specific role of the funding/sponsoring agency.     
  - **`grant_no`** (*grant_no*) Grant or award number. 

- **`curators`** (*curators*) A list of persons and/or organizations in charge of curating the resources associated with the project.
  - **`name`** (*name*) The name of the person or organization.  
  - **`role`** (*role*) The specific role of the person or organization in the curation of the project resources.
  - **`affiliation`** (*affiliation*) The affiliation of the person or organization.
  - **`abbreviation`** (*abbreviation*) An acronym of the organization, if an organization was entered in `name`.
  - **`email`** (*email*) The email address of the person or organization. The use of personal email addresses must be avoided.
  - **`url`** (*url*) A link to the website of the person or organization. 

- **`reviews_comments`** (*reviews_comments*) Many research projects will be subject to a review process, which may happen at different stages of the project implementation (from design to review of the final output). This block is intended to document the comments received by reviewers during this process. It is a repeatable block of metadata elements, which can be used to document comments with a fine granularity. 
  - **`comment_date`** (*comment_date*) The date the comment was provided, in ISO 8601 format (YYYY-MM-DD or YYYY-MM).
  - **`comment_by`** (*comment_by*) The name of the person or organization that provided the comment. 
  - **`comment_description`** (*comment_description*) The comment itself, in its original formulation or in a summary version.
  - **`comment_response`** (*comment_response*) The response provided by teh research team/person to the comment, in its original formulation or in a summary version.
  
- **`acknowledgments`** (*acknowledgments*) This repeatable block of elements is used to provide an itemized list of persons and organizations whose contribution to the project must be acknowledged. Note that specific metadata elements are available for listing financial sponsors and main contributors to the study. 
An alternative to this field is the `acknowledgment_statement` field (see below) which can be used to provide the acknowledgment in the form of an unstructured text.
  - **`name`** (*name*) The name of the person or agency being recognized for supporting the project.
  - **`affiliation`** (*affiliation*) The affiliation of the person or agency being acknowledged.
  - **`role`** (*role*) A brief description of the role of the person or agency that is being recognized or acknowledged for supporting the project.

- **`acknowledgement_statement`** (*acknowledgement_statement*) This field is used to provide acknowledgments in the form of an unstructured text. An alternative to this field is the *acknowledgments* field which provides a solution to itemize the acknowledgments. 

- **`disclaimer`** (*disclaimer*) Disclaimers limit the responsibility or liability of the publishing organization or researchers associated with the research project. Disclaimers assure that any research in the public domain produced by an organization has limited repercussions to the publishing organization. A disclaimer is intended to prevent liability from any effects occurring as a result of the acts or omissions in the research. 
                                                             
- **`confidentiality`** (*confidentiality*) A confidentiality statement binds the publisher to ethical considerations regarding the subjects of the research. In most cases, the individual identity of an individual that is the subject of research can not be released and special effort is required to assure the preservation of privacy.

- **`citation_requirement`** (*citation_requirement*) The citation requirement is specific to the output and is a preferred shorthand or means to refer to the publication or published good.

- **`related_projects`** (*related_projects*) The objective of this block is to provide links (URLs) to other, related projects which can be documented and disseminated in the same catalog or any other location on the internet.
  - **`name`** (*name*) The name (title) of the related project.
  - **`uri`** (*uri*) A link (URL) to the related project web page.
  - **`note`** (*note*) A brief description or other relevant information on the related project. 
 
- **`geographic_units`** (*geographic_units*) The geographic areas covered by the project. When the project relates to one or more countries, or part of one or more countries, it is important to provide the country name. This means that for a project related to a specific province or town of a country, the country name will be entered in addition to the province or town (as separate entries in this repeatable block of elements). Note that the area does not have to be an administrative area; it can for example be an ocean.
  - **`name`** (*name*) The name of the geographic area.
  - **`code`** (*code*) The code of the geographic area. For countries, it is recommended to use the [ISO 3166](https://en.wikipedia.org/wiki/List_of_ISO_3166_country_codes) country codes and names. 
  - **`type`** (*type*) The type of geographic area.

- **`keywords`** (*keywords*) A list of keywords that provide information on the core scope and objectives of the research project. Keywords provide a convenient solution to improve the discoverability of the research, as it allows terms and phrases not found elsewhere in the metadata to be indexed and to make a project discoverable by text-based search engines. A controlled vocabulary will preferably be used (although not required), such as the [UNESCO Thesaurus](http://vocabularies.unesco.org/browser/thesaurus/en/). The list provided here can combine keywords from multiple controlled vocabularies, and user-defined keywords.  
  - **`name`** (*name*) The keyword itself.
  - **`vocabulary`** (*vocabulary*) The controlled vocabulary (including version number or date) from which the keyword is extracted, if any.
  - **`uri`** (*uri*) The URL of the controlled vocabulary from which the keyword is extracted, if any.

- **`themes`** (*themes*) A list of themes covered by the research project. A controlled vocabulary will preferably be used. Note that `themes` will rarely be used as the elements `topics` and `disciplines` are more appropriate for most uses. This is a block of five fields:
  - **`id`** (*id*) The ID of the theme, taken from a controlled vocabulary.
  - **`name`** (*name*) The name (label) of the theme, preferably taken from a controlled vocabulary.
  - **`parent_id`** (*parent_id*) The parent ID of the theme (ID of the item one level up in the hierarchy), if a hierarchical controlled vocabulary is used.
  - **`vocabulary`** (*vocabulary*) The name (including version number) of the controlled vocabulary used, if any.
  - **`uri`** (*uri*) The URL to the controlled vocabulary used, if any. 

- **`topics`** (*topics*) Information on the topics covered in the research project. A controlled vocabulary will preferably be used, for example the [CESSDA Topics classification](https://vocabularies.cessda.eu/vocabulary/TopicClassification), a typology of topics available in 11 languages; or the [Journal of Economic Literature (JEL) Classification System](https://en.wikipedia.org/wiki/JEL_classification_codes), or the [World Bank topics classification](https://documents.worldbank.org/en/publication/documents-reports/docadvancesearch). Note that you may use more than one controlled vocabulary. 
  This element is a block of five fields: 
  - **`id`** (*id*) The identifier of the topic, taken from a controlled vocabulary.
  - **`name`** (*name*) The name (label) of the topic, preferably taken from a controlled vocabulary.
  - **`parent_id`** (*parent_id*) The parent identifier of the topic (identifier of the item one level up in the hierarchy), if a hierarchical controlled vocabulary is used.
  - **`vocabulary`** (*vocabulary*) The name (including version number) of the controlled vocabulary used, if any.
  - **`uri`** (*uri*) The URL to the controlled vocabulary used, if any. 

- **`disciplines`** (*disciplines*) Information on the academic disciplines related to the content of the research project. A controlled vocabulary will preferably be used, for example the one provided by the list of academic fields in [Wikipedia](https://en.wikipedia.org/wiki/List_of_academic_fields). This is a block of five elements: 
  - **`id`**  (*id*) The identifier of the discipline, taken from a controlled vocabulary.
  - **`name`** (*name*) The name (label) of the discipline, preferably taken from a controlled vocabulary.
  - **`parent_id`** (*parent_id*) The parent identifier of the discipline (identifier of the item one level up in the hierarchy), if a hierarchical controlled vocabulary is used.
  - **`vocabulary`** (*vocabulary*) The name (including version number) of the controlled vocabulary used, if any.
  - **`uri`** (*uri*) The URL to the controlled vocabulary used, if any.

- **`repository_uri`** (*repository_uri*) In the process of producing the outputs of the research project, a researcher may want to share their source code for transparency and replicability. This repository provides information for finding the repository where the source code is kept. 
  - **`name`** (*name*) Name of the repository where code is hosted. 
  - **`type`** (*type*) Repository type e.g.GitHub, Bitbucket, etc.
  - **`uri`** (*uri*) URI of the project source code/script repository 

- **`license`** (*license*) Information on the license(s) attached to the research project resources, which defines their terms of use.
  - **`name`** (*name*) The name of the license.
  - **`uri`** (*uri*) The URL of the license, where detailed information on the license can be obtained.
  - **`note`** (*note*) Additional information on the license.

- **`copyright`** (*copyright*) Information on the copyright, if any, that applies to the research project metadata.

- **`technology_environment`** (*technology_environment*) This field is used to provide a description (as detailed as possible) of the computational environment under which the scripts were implemented and are expected to be reproducible. A substantial challenge in reproducing analyses is installing and configuring the web of dependencies of specific versions of various analytical tools. Virtual machines (a computer inside a computer) enable you to efficiently share your entire computational environment with all the dependencies intact. (https://ropensci.github.io/reproducibility-guide/sections/introduction/) 

- **`technology_requirements`** (*technology_requirements*) Software/hardware or other technology requirements needed to run the scripts and replicate the outputs
 
- **`reproduction_instructions`** (*reproduction_instructions*) Instructions to secondary analysts who may want to reproduce the scripts.

- **`methods`** (*methods*) A list of analytic, statistical, econometric, machine learning methods used in the project. The objective is to allow users to find projects based on a search on methods applied, e.g. answer a query like *"poverty prediction using random forest"*.
  - **`name`** (*name*) A short name for the method being described.
  - **`note`** (*note*) Any additional information on the method.

- **`software`** (*software*) This field is used to list the software and the specialized packages and libraries/packages that were used to implement the project and that are required to reproduce the scripts. The libraries that are loaded by the scripts (e.g., by the R *require* or *library* command) are included (not all their own dependencies, which will be assumed to be installed automatically).
  - **`name`** (*name*) The name of the software. 
  - **`version`** (*version*) The version of the software. 
  - **`library`** (*library*) A list of libraries/packages required to run the scripts. Note that the specific version of each package is not documented here; it is expected to be found in the script or in the reproduction instructions. 

- **`scripts`** (*scripts*) This field is used to describe the scripts written by the project authors. All scripts are expected to have been written using software listed in the field *software*.
  - **`file_name`** (*file_name*) Name of the script file (for R users, this will typically include files with extension [.R], for Stata users it will be files with extension [.do], for Python users ...). But this can also include other files related and required to run the scripts (for example lookup CSV files, etc.) This does not include the data files, which are described ina  specific field. 
  - **``zip_package``** (*zip_package*) If the script files have been saved as or in a compressed file (zip, rar, of equivalent), we provide here the name of the zip file containing the script. 
  - **`title`** (*title*) A title (label) given to the script file 
  - **`authors`** (*authors*) This is a repeatable block that allows entering a list of authors and co-authors of a script 
    - **`name`** (*name*) Name of the author (person or organization) of the script 
    - **`affiliation`** (*affiliation*) The affiliation of the author.
    - **`role`** (*role*) Specific role of the person or organization in the production of the script. 
  	
  - **`date`** (*date*) Date the script was produced, in ISO 8601 format (YYYY-MM-DD) 
  - **`format`** (*format*) File format 
  - **`software`** (*software*) Software used to run the script 
  - **`description`** (*description*) Brief description of the script 
  - **`methods`** (*methods*) Statistical/analytic methods included in the script 
  - **`dependencies`** (*dependencies*) Any dependencies (packages/libraries) that the script relies on. This field is not needed if dependencies were described in the `library` element. 
  - **`instructions`** (*instructions*) Instructions for running the script. Information on the sequence in which the scripts must be run is critical. 
  - **`source_code_repo`** (*source_code_repo*) Repository (e.g. GitHub repo) where the script has been published. 
  - **`notes`** (*notes*) Any additional information on the script.
  - **`license`** (*license*) License, if any, under which the script is published.
    - **`name`** (*name*) Name (label) of the license  
    - **`uri`** (*uri*) License URI 
                       
- **`data_statement`** (*data_statement*) An overall statement on the data used in the project. A separate field is provided to list and document the origin and key characteristics of the datasets.

- **`datasets`** (*datasets*) This field is used to provide an itemized list of datasets used in the project. The data are not documented here (specific metadata are available for documenting data of different types, like the DDI for microdata, the ISO 19139 for geographic datasets, etc.)
  - **`name`** (*name*) The dataset name (title) 
  - **`idno`** (*idno*) The unique identifier of the dataset
  - **`note`** (*note*) A brief description of the dataset.
  - **`access_type`** (*access_type*) The access policy pplied to the dataset.
  - **`license`** (*license*) The access license that applies to the dataset.
  - **`license_uri`** (*license_uri*) The URL of a web page where more information on the license can be obtained. 
  - **`uri`** (*uri*) The URI where the dataset (or a detailed description of it) can be obtained.

- **`contacts`** (*contacts*) The contacts element provides the public interface for questions associated with the research project. There could be various contacts provided depending upon the organization. It is important to assure that the proper contacts are provided to channel public inquiry. 
  - **`name`** (*name*) The name of the contact person that should be contacted depending on the role defined below. 
  - **`role`** (*role*) Role of the contact person. A research project may have contact persons depending on the output or some of the technical input. Some complex projects may have various data collection processes that have different processing channels and contacts. This section should provide for a key primary public interface that can refer the public inquiry or provide a collection of entry points. 
  - **`affiliation`** (*affiliation*) The organization or affiliation of the contact person. This is usually the organization that the contact person represents.
  - **`email`** (*email*) Email address of the responsible person, institution, or division in charge of the research project or output.
  - **`telephone`** (*telephone*) Phone number of the responsible institution or division of the research project or output. 
  - **`uri`** (*uri*) The URI of the agency or organization of the contact organization. This may be the same as the web page of the project or may be a permanent contact name at an institutional level and not project related. Eventually a project web site may be removed but there may still be need to have a contact. In this case, it is recommended to have a contact that is permanent.


### Tags


### External resources








