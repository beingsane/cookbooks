# NFS

Add NFS support

```bash
vagrant plugin install vagrant-winnfsd
```

```ruby
[...]
config.vm.synced_folder ".", "/vagrant", type: "nfs"
[...]
```

```bash
mkdir -p ~/.ssh 
touch ~/.ssh/authorized_keys
```
