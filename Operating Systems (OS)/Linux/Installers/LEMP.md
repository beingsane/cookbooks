## LEMP

	apt-get update
	apt-get install nginx

	ip addr show eth0 | grep inet | awk '{ print $2; }' | sed 's/\/.*$//'

	apt-get install mysql-server

	mysql_install_db
	mysql_secure_installation

	apt-get install php5-fpm php5-mysql

	vim /etc/php5/fpm/php.ini

	cgi.fix_pathinfo=0

	service php5-fpm restart

	vim /etc/nginx/sites-available/default

	service nginx restart
