# Update

```bash
sudo apt-get update
sudo apt-get upgrade
```

```bash
wget ftp://ftp.mozilla.org/pub/firefox/releases/31.0/linux-i686/en-US/firefox-31.0.tar.bz2

# or

wget ftp://ftp.mozilla.org/pub/firefox/releases/31.0/linux-x86_64/en-US/firefox-31.0.tar.bz2
```

```bash
tar -xjf firefox-31.0.tar.bz2
```

```bash
sudo rm -rf  /opt/firefox
sudo mv firefox /opt/firefox31
```

```bash
sudo ln -s /opt/firefox31/firefox /usr/bin/firefox
```

