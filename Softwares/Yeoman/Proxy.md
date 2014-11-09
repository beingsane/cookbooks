# Set proxy

	npm config set proxy http://username:password@ip:port
	npm config set https-proxy http://username:password@ip:port

Export

	export npm_config_proxy http://username:password@ip:port
	export npm_config_https_proxy http://username:password@ip:port

Show config

	npm config list

Third software

	npm install http-proxy

	npm --https-proxy=http://username:password@ip:port -g install karma
