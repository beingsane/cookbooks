# Http

##### AH00558

httpd: Could not reliably determine the server's fully qualified domain name, using 127.0.0.1. Set the 'ServerName' directive globally to suppress this message

```bash
sudo apachectl configtest

cat /etc/hosts
hostname

sudo vim /etc/apache2/httpd.conf

ServerName [hostname]
```

##### AH00015

Unable to open logs

```bash
```

##### AH00072

make_sock: could not bind to address 0.0.0.0:80

```bash
```
