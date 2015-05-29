# Oracle

#### Tablespace

```sql
CREATE TABLESPACE tbs_username_01
	DATAFILE 'tbs_username_f2.dat' SIZE 40M
	ONLINE;
```

#### User

```sql
CREATE USER username
	IDENTIFIED BY password
	DEFAULT TABLESPACE tbs_username_01

	QUOTA 20M on tbs_username_01;
```

```sql
DROP USER username CASCADE;
ALTER TABLESPACE tbs_username_01 OFFLINE;
DROP TABLESPACE tbs_username_01 INCLUDING CONTENTS;
```

####

```sql
GRANT ALL ON table TO username;
```

GRANT SELECT ON table1 TO table2;

CREATE USER poweruser IDENTIFIED BY known_pwd;
GRANT create session TO poweruser;
GRANT create database link TO poweruser WITH ADMIN OPTION;

#### Procedure

GRANT create any procedure TO poweruser;
GRANT drop any procedure TO poweruser;
GRANT execute any procedure TO poweruser;

####

```sql
BEGIN
  FOR tables IN (SELECT table_name FROM all_tables WHERE owner = 'username1') LOOP
    execute IMMEDIATE
      'GRANT SELECT ON table.' ||tables.table_name|| ' TO username2';
  END loop;
END;
```

```sql
GRANT CREATE SESSION TO username;

GRANT CREATE SESSION TO username WITH ADMIN OPTION;
```

```sql
GRANT DBA TO username;
```

```sql
ALTER USER username IDENTIFIED BY password;
```

```sql
UPDATE table SET column = LTRIM(RTRIM(column));

UPDATE table SET column = REPLACE(column, ' ', '');
```

```sql
SELECT * FROM all_tab_privs;
SELECT * FROM dba_sys_privs;
SELECT * FROM dba_role_privs;
```

ALTER USER username GRANT CONNECT THROUGH username;

CREATE SYNONYM TABLE FOR UserA.TABLE;

SELECT FILE_NAME, BLOCKS, TABLESPACE_NAME FROM DBA_DATA_FILES;
