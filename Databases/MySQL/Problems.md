# Problems

#### Connection Failed

Host 'IP_ADDRESS' is not allowed to connect to this MySQL server

```bash
```

#### ERROR 2002 (HY000)

Can't connect to local MySQL server through socket '/tmp/mysql.sock' (2)

```
mysqld stop
touch /tmp/mysql.sock
mysqld_safe restart
```

##### OS X

```
rm -rf /usr/local/var/mysql/macbook.local.err
mysql.server start
```
