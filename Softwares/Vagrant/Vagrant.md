# Vagrant

```bash
vagrant init ubuntu/trusty64
```

```ruby
config.vm.hostname = "chromium"
config.vm.network "private_network", ip: "192.168.33.10"
config.vm.synced_folder ".", "/vagrant", type: "nfs"
config.vm.provider "virtualbox" do |vb|
  [...]
  vb.memory = "1024"
end
```

```bash
vagrant up --provider virtualbox
```

#### Symbolic Link

```bash
vagrant ssh

cd; ln -s /vagrant/www .
```
