# Vagrant

Add user

```bash
id

adduser <username>
usermod -aG sudo <username>
usermod -aG vagrant <username>
```

Set hostname

```ruby
config.vm.hostname = "chromium"
```

More memory for VM

```ruby
config.vm.provider "virtualbox" do |vb|
  [...]
  vb.memory = "2048"
end
```
