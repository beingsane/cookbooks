## Install Automatic

	sudo apt-get update
	sudo apt-get install -y python-software-properties python g++ make
	sudo apt-get install software-properties-common
	sudo add-apt-repository -y ppa:chris-lea/node.js
	sudo apt-get update
	sudo apt-get install nodejs

## Install Manual

	sudo apt-get install g++ curl libssl-dev apache2-utils
	
	wget -N http://nodejs.org/dist/node-latest.tar.gz
	
	tar -xf node-latest.tar.gz
	
	cd node-...
	
	./configure
	
	make
	
	sudo make install
