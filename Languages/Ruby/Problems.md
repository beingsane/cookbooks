## Problems

ERROR: Could not find a valid gem 'rake' (>= 0), here is why: windows

	gem sources -a http://rubygems.org
	gem install rake

WARNING:  Unable to pull data from 'https://rubygems.org/': SSL_connect returned=1 errno=0 state=SSLv3 read server certificate B: certificate verify failed (https://rubygems.org/latest_specs.4.8.gz)

	rvm get stable
	rvm osx-ssl-certs update all
	rvm rubygems latest
