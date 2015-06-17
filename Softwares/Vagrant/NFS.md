# NFS


### Windows

Add NFS support for Windows

```bash
vagrant plugin install vagrant-winnfsd
```

##### Vagrant File

```ruby
config.vm.synced_folder ".", "/vagrant", type: "nfs"
```

#### Bindfs

Inside VM

```bash
sudo apt-get update
sudo apt-get install -y bindfs
```

##### Vagrant File

```ruby
config.vm.synced_folder ".", "/vagrant", type: "nfs"

config.bindfs.bind_folder "/vagrant", "/vagrant", u: "vagrant", g: "www-data"
```
