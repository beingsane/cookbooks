## Purge

Purge nginx

	service nginx stop

	apt-get remove nginx
	apt-get remove --auto-remove nginx

	apt-get purge nginx
	apt-get purge --auto-remove nginx

	rm -rf /var/www/
	rm -rf /usr/share/nginx/

Purge php-fpm

	service php5-fpm stop

	apt-get remove php5-fpm
	apt-get remove --auto-remove php5-fpm

	apt-get purge php5-fpm
	apt-get purge --auto-remove php5-fpm

	rm -rf /etc/php5/

Purge php

	apt-get remove php*
	apt-get remove --auto-remove php

	apt-get purge php*
	apt-get purge --auto-remove php

	rm -rf /etc/php5/

Find

	find "$(cd ..; pwd)" -name "filename"

### Problems

E: dpkg was interrupted, you must manually run 'sudo dpkg --configure -a' to correct the problem.

	sudo dpkg --configure -a
