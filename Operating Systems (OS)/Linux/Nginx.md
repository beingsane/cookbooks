# Nginx

Simulate a install to see what will be install and check version of Nginx:

```bash
apt-get -s install nginx
apt-cache policy nginx
```

Install Nginx

```bash
sudo apt-get install -y nginx
sudo service nginx restart
```

Show IP address

```bash
ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'
```
