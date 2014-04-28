sqlite-to-mysql
===============

Script to convert and add sqlite3 database into a mysql/mariadb database

##Description##

This script is used to convert a sqlite3 .db file into a running mysql/mariadb 5.x+ instance.  It was adapted from the code posted at http://www.redmine.org/boards/2/topics/12793?r=24999 .  I've mostly simply altered it to make the effort of use minimal.

The script works as a layer between sqlite and mysql to format the sqlite dump, create a new user and database in mysql, and restore all the tables and data in one shell line.

##Dependencies##

A running flavor of MySQL.  This has been tested using MariaDB 5.5 in CentOS6.

Python 2.7

##Usage##

```bash
$ sqlite3 filename.db .dump | ./sqlite3-to-mysql.py -u new_user -p new_password -d new_database | mysql -u root -p --default-character-set=utf8

```

That's it!  Log into mysql database with your new user and your tables should be there and populated!

##Notes##

There isn't any forseeable reason for this not to work on Windows using sqlite.exe and mysql.exe, etc.  I have not testing this.

As always, use your common sense and backup your data before attempting this.  If you pick a database name that already exists in your mysql instance, expect the data to be overwritten.

Enjoy!
