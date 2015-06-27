# NVM

##### Ubuntu

```bash
sudo apt-get update
sudo apt-get install -y git

curl https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash

source ~/.bashrc

nvm ls-remote

nvm install stable
nvm alias default stable

node -v && npm -v
```

```bash
npm update -g
```

```bash
n=$(which node);n=${n%/bin/node}; chmod -R 755 $n/bin/*; sudo cp -r $n/{bin,lib,share} /usr/local
```
