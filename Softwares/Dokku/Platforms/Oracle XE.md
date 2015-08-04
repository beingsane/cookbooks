# Oracle XE

```bash
git clone git@github.com:MaksymBilenko/docker-oracle-xe-11g.git oracle
cd oracle
git remote add dokku dokku@domain.com:oracle
git push dokku master
```

```bash
sudo dokku volume:create oracle /home/oracle/data:/u01/app/oracle
dokku volume:link oracle oracle
```

```bash
sudo git clone https://github.com/stuartpb/dokku-bind-port.git /var/lib/dokku-alt/plugins/bind-port
```

```bash
dokku bind:create oracle 1521
```
