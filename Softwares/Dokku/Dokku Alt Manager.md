# Dokku Alt Manager

```bash
dokku manager:install
dokku manager:enable
```

#### Problems

> SQLSTATE[42S02]: Base table or view not found: 1146 Table 'dam._db_update' doesn't exist

```bash
dokku mariadb:console dam dam

CREATE TABLE _db_update (status varchar(255), name varchar(255));
exit

dokku manager:upgrade
```


https://github.com/romaninsh/dokku-alt-manager/issues/14