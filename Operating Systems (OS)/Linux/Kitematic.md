# Kitematic

#### Ubuntu

```bash
# install docker
curl -sSL https://get.docker.com/ubuntu/ | sudo sh
# add my user to docker group
sudo gpasswd -a ${USER} docker


# restart docker
sudo service docker restart
# tell the current terminal about the new docker group changes
newgrp docker

# download kitematic to /opt/kitematic
cd /opt
sudo git clone https://github.com/zedtux/kitematic
cd kitematic/
sudo git checkout linux-support
sudo make

# adjust permissions so that anyone in docker group may use kitematic
chmod -R g+w .
chgrp -R docker .

# start kitematic
npm start
```
