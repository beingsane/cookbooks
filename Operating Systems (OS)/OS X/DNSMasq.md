# DNSMasq

### [Installation](https://echo.co/blog/os-x-1010-yosemite-local-development-environment-apache-php-and-mysql-homebrew)

```bash
brew install -v dnsmasq
```

```bash
echo 'address=/.dev/127.0.0.1' > $(brew --prefix)/etc/dnsmasq.conf
```

```bash
echo 'listen-address=127.0.0.1' >> $(brew --prefix)/etc/dnsmasq.conf
```

```bash
echo 'port=35353' >> $(brew --prefix)/etc/dnsmasq.conf
```

```bash
brew services start dnsmasq
```

```bash
sudo mkdir -v /etc/resolver 

sudo bash -c 'echo "nameserver 127.0.0.1" > /etc/resolver/dev'

sudo bash -c 'echo "port 35353" >> /etc/resolver/dev'
```
