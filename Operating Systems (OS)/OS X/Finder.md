# Finder

#### Show/Hide Hidden Files

```bash
defaults write com.apple.finder AppleShowAllFiles YES
killall Finder /System/Library/CoreServices/Finder.app
```

###### Aliases

```bash
sudo vim ~/.bash_profile

alias showFiles='defaults write com.apple.finder AppleShowAllFiles YES; killall Finder /System/Library/CoreServices/Finder.app'
alias hideFiles='defaults write com.apple.finder AppleShowAllFiles NO; killall Finder /System/Library/CoreServices/Finder.app'

source ~/.bash_profile
```
