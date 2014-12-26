# NAT

Improve internet connection

```ruby
config.vm.provider "virtualbox" do |vb|
  [...]
  vb.customize ["modifyvm", :id, "--natdnshostresolver1", "on"]
  vb.customize ["modifyvm", :id, "--natdnsproxy1", "on"]
end
```
