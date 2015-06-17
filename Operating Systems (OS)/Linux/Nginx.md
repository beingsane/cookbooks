# Nginx

```bash
sudo apt-get install nginx

sudo service nginx restart
```

Show IP address

```bash
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```
