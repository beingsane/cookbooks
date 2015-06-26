# Export

#### Export MySQL database

```bash
mysqldump -u username -p database > backup.sql
```

#### Export MySQL database (PostgreSQL)

```bash
mysqldump -u username --extended-insert=FALSE --no-create-info --compact --compatible=postgresql database > file.sql
```

Convert MySQL to PostgreSQL

```bash
sed "s/\\\'/\'\'/g" file.sql > file1.sql
```

#### Import file to PostgreSQL

```bash
psql database < file1.sql
```
