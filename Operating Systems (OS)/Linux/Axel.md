# Axel

```bash
apt-get install axel
```

```bash
wget http://wilmer.gaast.net/downloads/axel-1.0b.tar.gz

tar -zxvf axel-1.0b.tar.gz

./configure

make install
```

```bash
axel --help
```

```bash
axel -n 8 url
```

## Custom configuration

```bash
vim ~/.axelrc

http_proxy = http://username:password@ip:port
```
