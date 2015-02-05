## Submodules

```bash
touch .gitmodules
```

Add submodule

```bash
git submodule add repo_url path/to/module
```

Remove folder/module from git repository

```bash
git rm -r --cached path/of/module
```

Update from submodule folder

```bash
cd path/of/module
git pull
```

Update all submodules

```bash
git submodule foreach git pull origin master
```

Close with submodules

```bash
git clone --recursive repo_url
git submodule foreach git checkout master
```

Get submodules from cloned repo

```bash
git submodule update --init --recursive
git submodule foreach git pull origin master
git submodule foreach git checkout master
```
