# Squid

```bash
git clone git@github.com:sameersbn/docker-squid.git squid
cd squid
```

```conf
cache_dir ufs /var/spool/squid3 100 16 256
```

```bash
git remote add dokku dokku@domain.com:squid
git push dokku master
```

```bash
sudo dokku volume:create squid /home/squid/cache:/var/spool/squid3
dokku volume:link squid squid
```

```bash
sudo git clone https://github.com/stuartpb/dokku-bind-port.git /var/lib/dokku-alt/plugins/bind-port
```

```bash
dokku bind:create squid 3128
```

### Log

```bash
sudo dokku volume:create squid_log /home/squid/log:/var/log/squid3
dokku volume:link squid squid_log
```

## Proxy

### Docker

```bash
sudo vim /etc/default/docker
```

```ini
export ftp_proxy="http://172.17.42.1:3128"
export http_proxy="http://172.17.42.1:3128"
export https_proxy="http://172.17.42.1:3128"
```

```bash
sudo service docker restart
```

### OS

