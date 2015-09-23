# Pyenv

## OS X

```bash
brew install pyenv
```

```bash
echo '\nif which rbenv > /dev/null; then eval "$(pyenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc
```

```bash
pyenv install --list
```

```bash
pyenv install 3.4.3
pyenv rehash
```

```bash
pyenv versions
```

```bash
pyenv local 3.4.3
pyenv global 3.4.3
```

More commands on [GitHub repository](https://github.com/yyuu/pyenv/blob/master/COMMANDS.md).
