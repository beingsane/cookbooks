# General

Only repository

```bash
git config --bool core.bare true
```

## SSH key

Generate SSH key

```bash
ssh-keygen -t rsa -C "email@domain.com"
```

Access home folder

```bash
cd ~/.ssh/
```

Copy RSA key

```bash
cat id_rsa.pub
```

Fix Pull

```bash
git reset --hard HEAD
git clean -f -d
git pull
```
