# Xdebug

```bash
sudo apt-get install -y php5-xdebug
```

##### Apache

```bash
sudo find / -name xdebug.so
```

```bash
sudo vim /etc/php5/apache2/php.ini
```

```bash
html_errors = On
```

```bash
[xdebug]
zend_extension="/usr/lib/php5/20090626+lfs/xdebug.so"
	
xdebug.remote_enable=on
xdebug.remote_handler=dbgp
xdebug.remote_host=localhost
xdebug.remote_port=9000
	
xdebug.var_display_max_depth=10
xdebug.var_display_max_data=1024
xdebug.var_display_max_children=1024
```

```bash
sudo service apache2 restart
```
