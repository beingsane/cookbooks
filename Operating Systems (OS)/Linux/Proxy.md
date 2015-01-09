# Proxy

```bash
export HTTP_PROXY=http://username:password@ip:port
export HTTPS_PROXY=http://username:password@ip:port
```

```bash
visudo

Defaults	env_reset
Defaults	env_keep="http_proxy ftp_proxy" 
```
