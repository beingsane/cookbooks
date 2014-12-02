## Permissions

	ll /var/run/php5-fpm.sock

	srw-rw---- 1 www-data www-data 0 Aug  6 14:16 /var/run/php5-fpm.sock=

	vim /etc/php5/fpm/pool.d/www.conf

	listen.owner = www-data
	listen.group = www-data
	listen.mode = 0660

	sudo service php5-fpm restart