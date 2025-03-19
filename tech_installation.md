# Installation on a server

[why good to install on server]

## Hardware requirements


## Software requirements

The Metadata Editor requires PHP with a MySQL or MariaDB database. For data import/export, Python 3 is required.

### Web server

- Apache 2.4 or later
- IIS 6/7.x or later
- NGINX

### PHP (8.1 or later)

Required PHP extensions:
- xsl
- xml
- mbstring
- mysqli

### Supported databases

- MySQL 8.x or MariaDb

### Python (3.12)
A Python/FastApi backend REST API service for data import/export, summary statistics for Stata, SPSS and CSV files.


## Downloading the source code

The editor installation requires the following:
- Metadata Editor (PHP application with MySQL database)
- Python backend API

Follow the steps to download and install editor frontend and backend app. The resulting folder structure will look like this:

```
metadata_editor
│
+--editor
+--pydatatools
```

For downloading the source code, you can either download the zipped packages or use Git.

**Option 1 (Use git):** Navigate to the web server folder where you want to setup the project and run the following commands:

```
$ mkdir metadata_editor
$ cd metadata_editor

$ git clone https://github.com/ihsn/editor
$ git clone https://github.com/mah0001/pydatatools
```

**option 2 (Zip packages):** Download the zip packages and unzip to create the above folder structure.

- Metadata editor: https://github.com/ihsn/editor/archive/refs/heads/main.zip
- PyDataTools: https://github.com/mah0001/pydatatools/archive/refs/heads/main.zip
 

## Configuring the database

The Metadata Editor comes with a web based installer. Before you can run the installer:

 - Create a new database (e.g. metadata_editor)
 - Create a database user account with password and limit user access to the metadata editor database only
   

### Updating the database configuration

1. Open `editor/application/config` folder and rename/copy `database.sample.php` to `database.php`
2. Open `database.php` file in a text editor like Notepad or Notepad++, and fill:

`hostname` - ip address or the machine name where database is hosted

`username` - database user name 

`password` - database password

`database` - database name


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

3. Save the file

### Setting folder permissions

Run the following commands to set read/write permissions for the folders where the data will be stored:

```
$ chmod -R 775 datafiles files logs
```


### Running the installer

- Open web browser to the location of the Editor installation. For example: http://your-domain/editor-folder-name, or http://localhost/editor-folder-name.

- Check that all settings are marked with a green tick and fix any that are not on your webserver before running the installer.

- Click on the Install Database button and complete the form to create an initial Site Administrator account.


**Note:** Create a complex password at least 12 characters long with some uppercase, punctuation and numbers to aid security of your site. 


## Installing Pydatatools (Python/FastApi)

The Pydatatools application requires Python. Install **Python 3.12** from here, https://www.python.org/downloads/.

If you have not downloaded the `Pydatatools` yet, download from Github - https://github.com/mah0001/pydatatools


### Installing dependencies

To install the packages and libraries required by the `Pydatatools`, navigate to the `pydatatools` folder and run from command line:

```python

  $ pip install -r requirements.txt

```


## Running/starting Pydatatools
To start the FastAPI service, first navigate to the folder `pydatatools` via command line and run:

```
$ nohup python -m uvicorn main:app --reload --host 0.0.0.0 --port 8000 &
```

## Configuring a user authentication system


