# Apache

##### Error: AH00558

httpd: Could not reliably determine the server's fully qualified domain name, using 127.0.0.1. Set the 'ServerName' directive globally to suppress this message

```bash
sudo apachectl configtest

cat /etc/hosts
hostname

sudo vim /etc/apache2/httpd.conf

ServerName [hostname]
```

##### How enable server-status

In order to handle requests to /server-status with mod_status, you will need the following lines somewhere in your configuration:

```bash
apachectl -t -D DUMP_MODULES | grep status
sudo vim /etc/apache2/httpd.conf
```

```
<Location /server-status>
  SetHandler server-status
</Location>
```

```bash
sudo apachectl restart
sudo apachectl status
```

Don't forget to restrict access to localhost or other trusted hosts using Allow/Deny or the newer Require directives.

##### Enable PHP

```bash
sudo vim /etc/apache2/httpd.conf

LoadModule php5_module libexec/apache2/libphp5.so
```

##### Enable vhost

```bash
sudo vim /etc/apache2/httpd.conf

LoadModule vhost_alias_module libexec/apache2/mod_vhost_alias.so
Include /private/etc/apache2/extra/httpd-vhosts.conf
```

##### Make php.ini

```bash
php --ini

sudo cp /private/etc/php.ini.default /private/etc/php.ini

sudo apachectl restart
```

##### Change php.ini settings

```bash
sudo vim /private/etc/php.ini
```

##### Change default PHP of apache

```bash
brew info php56

sudo vim /etc/apache2/httpd.conf

LoadModule php5_module /usr/local/opt/php56/libexec/apache2/libphp5.so
```

##### OS X

```bash
sudo /usr/sbin/apachectl start
sudo /usr/sbin/apachectl stop
sudo /usr/sbin/apachectl restart
```
