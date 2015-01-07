# Import box

```bash
cd $HOME/.vagrant.d/boxes

mkdir -p laravel-VAGRANTSLASH-homestead/0.2.2/virtualbox

cd laravel-VAGRANTSLASH-homestead

echo 'https://vagrantcloud.com/laravel/homestead' >> metadata_url

cd 0.2.2/virtualbox

echo '{"provider":"virtualbox"}' >> metadata.json
```
