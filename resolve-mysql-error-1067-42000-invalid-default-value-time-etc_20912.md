# Resolve MySql ERROR 1067 (42000) Invalid default value (time, etc)

## Linux CLI

1. `$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf`
1. Find line containing `sql_mode`
   1. If found, remove `NO_ZERO_IN_DATE` and `NO_ZERO_DATE` items from it, go to _step 3_
   1. If NOT found
      1. Exit nano, `$ mysql -u username -p`, enter your password for your `username`
      1. `mysql> show variables like 'sql_mode';`
      1. copy all items presented against `sql_mode` **except `NO_ZERO_IN_DATE` and `NO_ZERO_DATE`** e.g. copied items will be `ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION`
      1. `mysql> exit`
      1. `$ sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf`
      1. Paste this line at the end `sql_mode=ONLY_FULL_GROUP_BY,STRICT_TRANS_TABLES,ERROR_FOR_DIVISION_BY_ZERO,NO_AUTO_CREATE_USER,NO_ENGINE_SUBSTITUTION` (items after `=` are copied in _step c_)
1. Save file and exit from nano
1. `sudo service mysql restart`
1. Now try whatever that led to this particular error which should now be resolved.


Tags: mysql, ubuntu, linux, windows

[Permalink](https://quickhowto.github.io/mysql/resolve-mysql-error-1067-42000-invalid-default-value-time-etc_20912)
