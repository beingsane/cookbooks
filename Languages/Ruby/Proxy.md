## Proxy

Try install rake

```bash
gem install rake
```

If get error

```bash
ERROR:  http://rubygems.org/ does not appear to be a repository
ERROR:  Could not find a valid gem 'rake' (>= 0) in any repository
```

Open bashrc file

```bash
vim ~/.bashrc
```

Set http proxy

```bash
export http_proxy=http://username:password@ip:port
```

Reload bashrc file

```bash
source .bashrc
```

Keep env

```bash
sudo visudo

Defaults env_keep += "http_proxy https_proxy ftp_proxy"
sudo env | grep http_proxy
```
