# OS X

### [Installation](https://echo.co/blog/os-x-1010-yosemite-local-development-environment-apache-php-and-mysql-homebrew)

```bash
brew update
brew doctor
brew upgrade
```

```bash
brew install -v mysql
```

```bash
cp -v $(brew --prefix mysql)/support-files/my-default.cnf $(brew --prefix)/etc/my.cnf
```

```bash
cat >> $(brew --prefix)/etc/my.cnf <<'EOF'
 
# Echo & Co. changes
max_allowed_packet = 1073741824
innodb_file_per_table = 1
EOF
```

```bash
sed -i '' 's/^#[[:space:]]*\(innodb_buffer_pool_size\)/\1/' $(brew --prefix)/etc/my.cnf
```

```bash
brew tap homebrew/services
```

```bash
brew services start mysql
```

```bash
$(brew --prefix mysql)/bin/mysql_secure_installation
```
