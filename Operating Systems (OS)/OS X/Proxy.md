# Proxy

```bash
vim .zshrc

export http_proxy=http://username:password@ip:port
export https_proxy=$http_proxy
export all_proxy=$http_proxy
```

The environment variable `HTTP_PROXY` is discouraged.  Use `http_proxy`.
