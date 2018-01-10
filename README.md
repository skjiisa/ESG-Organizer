# ESG-Organizer

Elder Scrolls Game Organizer

A PHP web app for organizing mods and characters in Elder Scrolls Games.

This is curretnly in extremely early versions and is not properly usable.
Major changes to database and file structure are likely to come, breaking any use of it in its current state.

## Install

### Requirements

* PHP 5.7 or above
* MySQL or MariaDB
* Server configured to run PHP files without the .php extention in the URL

### Set up database

Log into MySQL (or MariaDB) as root and create the `esgorganizer` databse.

	CREATE DATABASE esgorganizer;
	USE esgorganizer;

Create the `esguser` and give it priviliges. Make sure to assign a password in place of `[password]`.

	CREATE USER 'esguser'@'localhost' IDENTIFIED BY '[password]';
	GRANT ALL PRIVILEGES ON esgorganizer.* TO 'esguser'@'localhost';

### Install and configure files

Copy the `esgo_includes` folder to a location on your web server, preferably _outside_ of your web root.

Copy the contents of the `html` folder to somewhere in your webroot. It does not have to be in the root. Edit the `includes.php` file to direct the location of files (instructions given in file).

Edit the value of the `$dbpass` variable in `esgo_includes/db_connection.php` to the password given to `esguser` in the databse..

Open the `install.php` to create the database tables and populate them with default values.