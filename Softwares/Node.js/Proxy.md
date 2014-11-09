## Proxy configurations

List configurations

	npm config list

Set registry URL

	npm config set registry http://registry.npmjs.org/

Set proxy

	npm config set http-proxy http://username:password@ip:port
	npm config set https-proxy http://username:password@ip:port

Remove proxy
	
	npm config delete http-proxy
	npm config delete https-proxy
