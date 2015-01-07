# Rbenv

```bash
brew install rbenv ruby-build rbenv-gem-rehash
echo '\nif which rbenv > /dev/null; then eval "$(rbenv init -)"; fi' >> ~/.zshrc
source ~/.zshrc

rbenv install --list
rbenv install 2.1.2
rbenv rehash
rbenv global 2.1.2
```
