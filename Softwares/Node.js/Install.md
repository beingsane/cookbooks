## Install Automatic

	apt-get update
	apt-get install -y python-software-properties python g++ make
	apt-get install software-properties-common
	add-apt-repository -y ppa:chris-lea/node.js
	apt-get update
	apt-get install nodejs

## Install Manual

	apt-get install g++ curl libssl-dev apache2-utils
	
	wget -N http://nodejs.org/dist/node-latest.tar.gz
	
	tar -xf node-latest.tar.gz
	
	cd node-...
	
	./configure
	
	make
	
	make install
