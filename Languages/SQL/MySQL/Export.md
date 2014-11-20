## Export

Export MySQL database

	mysqldump -u user  --extended-insert=FALSE --no-create-info --compact --compatible=postgresql database > file.sql

Convert MySQL to PostgreSQL

	sed "s/\\\'/\'\'/g" file.sql > file1.sql

Import file to PostgreSQL

	psql database < file1.sql
