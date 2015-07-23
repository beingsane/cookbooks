# Installer

##### Ubuntu

```bash
sudo apt-get install postgresql postgresql-contrib
```

```bash
dpkg -l | grep postgres
```

###### Remove

```bash
sudo apt-get --purge remove postgresql postgresql-doc postgresql-common
```

##### OS X

Installation:

```bash
brew install postgres
```

Create database:

```bash
initdb /usr/local/var/postgres
```

Run on startup:

```bash
mkdir -p ~/Library/LaunchAgents
ln -sfv /usr/local/opt/postgresql/*.plist ~/Library/LaunchAgents
launchctl load ~/Library/LaunchAgents/homebrew.mxcl.postgresql.plist
```

Show running status:

```bash
ps auxwww | grep postgres

pg_ctl -D /usr/local/var/postgres status

pg_ctl -D /usr/local/var/postgres -l /usr/local/var/postgres/server.log start
```
