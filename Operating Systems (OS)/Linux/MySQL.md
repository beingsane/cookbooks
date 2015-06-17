# MySQL

```bash
sudo apt-get install mysql-server php5-mysql
```

```bash
sudo mysql_install_db
```

```bash
sudo /usr/bin/mysql_secure_installation
```

##### What is that?

```bash
sudo debconf-set-selections <<< 'mysql-server mysql-server/root_password password root'
sudo debconf-set-selections <<< 'mysql-server mysql-server/root_password_again password root'
```
