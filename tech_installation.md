# Installation on a server

The Metadata Editor can be installed on a server or on a stand-alone personal computer (PC). For installation on a PC, see the section *Installation on a personal computer*. 

## Why install on a server?

Installing the Metadata Editor on a web server provides several advantages:
- **Collaboration**: Multiple users can work on metadata simultaneously.
- **Scalability**: Allows for efficient handling of larger datasets and multiple concurrent users.
- **Accessibility**: Users can access the application from any device with a browser.
- **Centralization of metadata**: If the Metadata Editor runs on an organization's server (typically, on its intranet), all metadata will be stored ina central location. the Metadata Editor can therefore operate as a corporate metadata repository.
- **Permission control**: Running the application on a server allows configuration of an organization's user authentication system.
- **Security**: Centralizing the generation and storage of the metadata on a server facilitates the management of backups and implementation of other security measures. 

## System requirements

### Hardware requirements

Ensure your server meets the following minimum specifications:
- CPU: Dual-core processor or higher
- RAM: At least 4 GB (8 GB recommended for larger datasets)
- Storage: Minimum 20 GB of free disk space

### Software requirements

To run the Metadata Editor, you will need:

**Web server**:
- Apache 2.4 or later
- IIS 6/7.x or later
- NGINX
- PHP: Version 8.1 or later, with the following required extensions:
  - xsl
  - xml
  - mbstring
  - mysqli

**Database**:
- MySQL 8.x or MariaDB. The database is not provided in the Metadata Editor package. The selected database application must be downloaded from its respective repository or website.

**Python**:
- Python 3.12 or later is required for running the FastAPI backend for data import/export and generating summary statistics for Stata, SPSS, and CSV files.


### Downloading and installing the Metadata Editor 

**Required components**

To install the Metadata Editor, you need:
- Metadata Editor: PHP application with a MySQL/MariaDB database.
- PyDataTools: Python backend API for data import/export and summary statistics.

**Folder structure** 

After installation, your directory structure should look like this:

```
metadata_editor
│
+--editor
+--pydatatools
```

**Downloading the source code**

- ***Option 1: Using Git***

Navigate to the web server directory where you want to install the project and run:

```
$ mkdir metadata_editor
$ cd metadata_editor

$ git clone https://github.com/ihsn/editor
$ git clone https://github.com/mah0001/pydatatools
```

- ***Option 2: Using Zip Packages***

   Download the zipped packages and extract them to create the required folder structure:

     - Metadata editor: https://github.com/ihsn/editor/archive/refs/heads/main.zip
    - PyDataTools: https://github.com/mah0001/pydatatools/archive/refs/heads/main.zip
  

**Configuring the database**

Step 1: Create Database and User
- Create a new database (e.g., metadata_editor).
- Create a database user with a secure password.
- Grant this user access to the metadata_editor database.

Step 2: Update Database Configuration
- Navigate to the editor/application/config/ folder.
- Copy or rename database.sample.php to database.php.
- Open database.php in a text editor and update the following fields:
   - `hostname` - ip address or the machine name where database is hosted
   - `username` - database user name 
   - `password` - database password
   - `database` - database name

```php

$db['default'] = array(
	'dsn'	=> '',
	'hostname' => 'localhost',
	'username' => 'nada_user',
	'password' => '<db-pass-here>',
	'database' => 'metadata_editor',
	'dbdriver' => 'mysqli',
	'dbprefix' => '',
	'pconnect' => FALSE,
	'db_debug' => FALSE,
	'cache_on' => FALSE,
	'cachedir' => '',
	'char_set' => 'utf8',
	'dbcollat' => 'utf8_general_ci',
	'swap_pre' => '',
	'encrypt' => FALSE,
	'compress' => FALSE,
	'stricton' => FALSE,
	'failover' => array(),
	'save_queries' => TRUE,
	'prefix_short_words'=>TRUE
);

```

Save the file.

**Setting folder permissions**

Run the following commands to set read/write permissions for the folders where the data will be stored:

```
$ chmod -R 775 datafiles files logs
```


**Running the installer**

- Open a web browser and navigate to the Editor installation URL. For example: http://your-domain/editor-folder-name, or http://localhost/editor-folder-name.
- Check that all settings are marked with a green tick and fix any that are not on your webserver before running the installer. 
- Click on the `Install Database` button and complete the form to create an initial Site Administrator account.
 
⚠️ Note: Use a complex password (at least 12 characters, including uppercase, numbers, and special characters) to enhance security.


**Installing and configuring PyDataTools (Python/FastAPI)**

- ***Step 1: Install Python*** 

  Download and install Python 3.12 from https://www.python.org/downloads/.

- ***Step 2: Install dependencies***

  Navigate to the pydatatools folder and run:

  ```python
	$ pip install -r requirements.txt
  ```

- ***Step 3: Run the FastAPI service***

  To start the FastAPI service, run:

   ```
	$ nohup python -m uvicorn main:app --reload --host 0.0.0.0 --port 8000 &

   ```

The Metadata Editor and PyDataTools should now be operational. This completes the installation process. 


### Configuring a user authentication system

Configure a user authentication system by:
