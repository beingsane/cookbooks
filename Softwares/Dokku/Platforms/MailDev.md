# MailDev

```bash
git clone git@github.com:yvess/docker-maildev.git maildev
cd maildev
git remote add dokku dokku@domain.com:maildev
git push dokku master
```

```bash
sudo git clone https://github.com/stuartpb/dokku-bind-port.git /var/lib/dokku-alt/plugins/bind-port
```

```bash
dokku bind:create maildev 25
```
