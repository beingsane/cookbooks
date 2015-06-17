# Apache

```bash
sudo apt-get update
sudo apt-get install -y apache2-mpm-event
sudo service apache2 status
sudo service apache2 start
```

##### Modules

```bash
sudo a2enmod rewrite
```

#####  Warnings

> AH00558: apache2: Could not reliably determine the server's fully qualified domain name, using 127.0.1.1. Set the 'ServerName' directive globally to suppress this message

```bash
echo "ServerName localhost" | sudo tee /etc/apache2/conf-available/servername.conf
sudo a2enconf servername
sudo service apache2 restart
```
