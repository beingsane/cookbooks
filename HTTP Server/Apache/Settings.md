# Settings

##### Cross-Origin Resource Sharing

> Font from origin 'http://domain.com' has been blocked from loading by Cross-Origin Resource Sharing policy: No 'Access-Control-Allow-Origin' header is present on the requested resource. Origin 'http://domain.com' is therefore not allowed access.

```bash
sudo a2enmod headers
```

```ini
<VirtualHost *:80>
    <Directory /var/www/project/web>
        Header set Access-Control-Allow-Headers "ORIGIN, X-REQUESTED-WITH, CONTENT-TYPE"
        Header set Access-Control-Allow-Methods "POST, GET, OPTIONS, PUT, DELETE"
        Header set Access-Control-Allow-Origin "*"
        Header set Access-Control-Allow-Credentials true
        Header set Access-Control-Max-Age 60000
    </Directory>
</VirtualHost>
```

```bash
sudo service apache2 restart
```
