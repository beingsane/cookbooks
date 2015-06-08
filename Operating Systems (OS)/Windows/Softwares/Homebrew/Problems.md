# Problems

##### Git problems

```bash
cd $(brew --repository)

git checkout -- .
sudo git reset --hard origin/master

brew doctor
```

##### Warning: The /usr/local directory is not writable.

```bash
sudo chown -R $USER /usr/local

brew doctor
```

##### [Cask](https://github.com/caskroom/homebrew-cask/blob/master/USAGE.md)

```bash
brew update && brew upgrade brew-cask && brew cleanup && brew cask cleanup

brew cask home wkhtmltopdf

brew cask uninstall wkhtmltopdf
```

#### Clear

```bash
brew cleanup
brew cleanup --cache
rm -rf brew --cache
brew prune
```


