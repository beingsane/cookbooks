# Private Bower

## Ubuntu

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash
su - $USER
nvm install stable
nvm use stable
nvm alias default stable
```

```bash
npm install -g private-bower
```

```bash
private-bower --config ./myBowerConfig.json
```

## Configuration

### Git

```bash
sudo apt-get install -y git-core
```

### Server

```bash
touch myBowerConfig.json
```

```json
{
  "port": 5678,
  "hostName": null,
  "registryFile": "./bowerRepository.json",
  "timeout": 144000,
  "public": {
    "disabled": false,
    "registry": "http://bower.herokuapp.com/packages/",
    "registryFile": "./bowerRepositoryPublic.json",
    "whitelist": [],
    "blacklist": []
  },
  "authentication": {
    "enabled": false,
    "key": "password"
  },
  "repositoryCache": {
    "cachePrivate": true,
    "git": {
      "enabled": true,
      "cacheDirectory": "./gitRepoCache",
      "host": "localhost",
      "port": 6789,
      "protocol": "git",
      "publicAccessURL": null,
      "refreshTimeout": 10,
      "parameters": {
        "timeout": 60000,
        "max-connections": 100
      }
    },
    "svn": {
      "enabled": false,
      "cacheDirectory": "./svnRepoCache",
      "host": "localhost",
      "port": 7891,
      "protocol": "svn",
      "publicAccessURL": null,
      "refreshTimeout": 10
    }
  },
  "proxySettings" : {
    "enabled": false,
    "host": "proxy",
    "username": "name",
    "password" : "pass",
    "port": 8080,
    "tunnel": false
  },
  "log4js" : {
    "enabled": false,
    "configPath" : "log4js.conf.json"
  }
}
```

### Project

```bash
touch .bowerrc
```

```json
{
  "registry": "http://yourPrivateBowerRepo:5678",
  "timeout": 300000
}
```
