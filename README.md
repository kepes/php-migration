# php-migration
Rails like migration in PHP

Can create empty migration SQL script and run this script on specific database if
the script never run on it. Migration sql file name must contains timestamp and a
description like '20150118140555_DatabaseStructure.sql'
The script create a database table called 'migrations' and store already processed
migration file timestamp into this tabel. On the next run it will not run already
processed scripts based on 'migrations' table.
If only one file specified instead of a folder migration will only work on that script
and timestamp check will not run.


Create migration file example:
 php migrate.php -c MyFirstMigration ./migrations/

Run pending migrations:
 php migrate.php -m 127.0.0.1 -d my_database -u username -p secret ./migrations/

Run one migration:
 php migrate.php -m 127.0.0.1 -d my_database -u username -p secret ./migrations/20150118140555_MyFirstMigration.sql
