# NFS


#### Windows

```bash
vagrant plugin install vagrant-winnfsd
```

##### Vagrant File

```ruby
config.vm.synced_folder ".", "/vagrant", type: "nfs"
```

#### Bindfs

##### Ubuntu

```bash
sudo apt-get update
sudo apt-get install -y bindfs
```

##### CentOS

```bash
sudo yum -y update
sudo yum install -y fuse fuse-devel
```

```bash
cd /usr/local/src
sudo wget http://bindfs.org/downloads/bindfs-1.12.6.tar.gz
sudo tar -xzf bindfs-*
cd bindfs-*
sudo ./configure && sudo make && sudo make install
cd .. && sudo rm -rf bindfs*
```

```bash
usermod -a -G fuse vagrant

exec /bin/bash
```

```bash
cat << EOF | sudo tee -a /etc/fuse.conf
user_allow_other
EOF
```

##### Vagrant File

```ruby
config.vm.synced_folder ".", "/vagrant", type: "nfs"

config.bindfs.bind_folder "/vagrant", "/vagrant", u: "vagrant", g: "www-data"
```
