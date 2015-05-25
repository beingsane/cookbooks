# Install

### OS X

```
brew install mysql
mysql.server restart
mysql_secure_installation
```

```
mysql.server stop
mysql_install_db --verbose --user=`whoami` --basedir="$(brew --prefix mysql)" --datadir=/usr/local/var/mysql --tmpdir=/tmp
```

```
sudo mkdir /var/mysql
sudo chmod 755 /var/mysql
sudo ln -s /tmp/mysql.sock /var/mysql/mysql.sock
```

```
mysql.server start
```
