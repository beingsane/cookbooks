# HTTP Server

```bash
sudo ln -s /vagrant/www /var/www
sudo chown -R `whoami`:www-data /var/www
ln -s /vagrant/www ~/www
sudo chown -R `whoami`:www-data ~/www
```

#### Nginx

```bash
cd /etc/nginx/sites-available
sudo cp default default.bkp
sudo vim default
```

```ini
root /var/www;
index index.php index.html index.htm;

location / {
	autoindex on;
}
```

```bash
sudo service nginx restart
```

Show current IP address

```bash
echo '<?php phpinfo();' >> /vagrant/www/info.php
ifconfig eth0 | grep inet | awk '{ print $2 }'
```
