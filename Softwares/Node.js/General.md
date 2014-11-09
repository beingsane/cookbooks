## General

Clean cache

	npm cache clean

### Fix issues with permissions

	sudo chown -R `whoami` ~/.npm
	
	sudo chown -R `whoami` /usr/lib/node_modules
	sudo chown -R `whoami` /usr/local/lib/node_modules
	sudo chown -R `whoami` /usr/local
	
	npm config set prefix ~/.npm

	export PATH="$PATH:$HOME/.npm/bin"

### Update NPM packages

	npm update -g

#### Install packages without symbolic links

	npm install --no-bin-links
