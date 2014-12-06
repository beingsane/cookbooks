## Ignore

*nix

	git config --global core.excludesfile '~/.gitignore'

Windows

	git config --global core.excludesfile "%USERPROFILE%\.gitignore"

Find and remove .DS_Store files

	find . -name .DS_Store -print0 | xargs -0 git rm -f --ignore-unmatch

Find and remove Thumbs.db files

	find . -name Thumbs.db -print0 | xargs -0 git rm -f --ignore-unmatch