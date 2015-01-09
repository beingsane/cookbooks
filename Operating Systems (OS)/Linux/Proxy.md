# Proxy

Set proxy in bash file:

```bash
export HTTP_PROXY=http://username:password@ip:port
export HTTPS_PROXY=http://username:password@ip:port
```

Set proxy in aptitude:

```bash
visudo

Defaults	env_reset
Defaults	env_keep="http_proxy ftp_proxy" 
```

**407  authenticationrequired**

```bash
sudo vim /etc/apt/apt.conf

Acquire::http::proxy "http://username:password@ip:port";
Acquire::https::proxy "http://username:password@ip:port";
Acquire::socks::proxy "http://username:password@ip:port";
```
