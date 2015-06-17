# Permissions

```ruby
config.vm.synced_folder ".", "/vagrant", id: "vagrant-root",
	owner: "vagrant",
	group: "www-data",
	mount_options: ["dmode=775,fmode=664"]
```
