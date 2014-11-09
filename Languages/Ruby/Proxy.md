## Proxy

Try install rake

	sudo gem install rake

If get error

	ERROR:  http://rubygems.org/ does not appear to be a repository
	ERROR:  Could not find a valid gem 'rake' (>= 0) in any repository

Open bashrc file

	sudo vim ~/.bashrc

Set http proxy

	export http_proxy=http://username:password@ip:port

Reload bashrc file

	source .bashrc

Keep env

	sudo visudo
	Defaults env_keep += "http_proxy https_proxy ftp_proxy"
	sudo env | grep http_proxy
