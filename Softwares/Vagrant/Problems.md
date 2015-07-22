# Problems

> The provider 'VIRTUALBOX' could not be found, but was requested to
back the machine 'default'. Please use a provider that exists.

```bash
mv .vagrant/machines/default/VIRTUALBOX .vagrant/machines/default/virtualbox
```

```bash
echo "export VAGRANT_DEFAULT_PROVIDER=virtualbox" >> ~/.bashrc
source ~/.bashrc
```
