# Oh My Zsh

```bash
sudo apt-get update
sudo apt-get install -y zsh curl wget git

sh -c "$(curl -fsSL https://raw.github.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

chsh -s `which zsh`
```

Set monokai syntax for zsh

```bash
vim ~/.zshrc
```

```ini
ZSH_THEME="wedisagree"
```

Set monokai syntax for Vim

```bash
mkdir -p ~/.vim/colors
wget https://raw.githubusercontent.com/sickill/vim-monokai/master/colors/monokai.vim -P ~/.vim/colors
echo -e "syntax enable\ncolorscheme monokai" >> ~/.vimrc
```

##### Problems

chsh: PAM: Authentication failure

```bash
sudo vim /etc/pam.d/chsh

#comment
auth required pam_shells.so

sudo chsh $USER -s $(which zsh)
```
