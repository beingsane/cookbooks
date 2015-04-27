# Bash

### Turn bash auto-load automatically

```bash
sudo vim ~/.profile
```

```
if [ -n "$BASH_VERSION" ]; then
    # include .bashrc if it exists
    if [ -f "$HOME/.bashrc" ]; then
        . "$HOME/.bashrc"
    fi
fi
```

### Color bash

```bash
sudo cp /root/.bashrc /home/edson/
souce ~/.bashrc
```
