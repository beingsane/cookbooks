##  Clarity

Install Ruby

	sudo apt-get install -y libmysqlclient-dev ruby-dev
	sudo apt-get install -y g++

Install gems

	sudo gem install mysql eventmachine eventmachine_httpserver json clarity

Start server

	sudo clarity --username=admin --password=admin --port=8989 /var/log

Command clearlog. Go to user home

	cd

Install Vim if not exists

	sudo apt-get install -y vim

Make alias

	alias clearlog='sudo rm -rf /var/log/apache2/*; sudo service apache2 restart'
	alias clearlog='sudo rm -rf /var/log/nginx/*; sudo service nginx restart'

Restart bash

	source .bashrc

Test command

	clearlog
