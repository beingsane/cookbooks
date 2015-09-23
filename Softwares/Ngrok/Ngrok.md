# Ngrok

```bash
wget -qO- -O tmp.zip https://dl.ngrok.com/ngrok_2.0.19_darwin_amd64.zip && unzip tmp.zip && rm tmp.zip
chmod +x ngrok
sudo mv ngrok /usr/local/bin
```

### Authtoken

Access [ngrok dashboard](https://dashboard.ngrok.com) and copy authtoken

```bash
ngrok authtoken <authtoken>
```

### Start

```bash
ngrok http 80
```

### Subdomian (paid)

```bash
ngrok http -subdomain=test 80
```
