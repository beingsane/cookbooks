## PEAR

PEAR ERROR: Syntax Error, unexpected '(' in Unknown on Line 14

Open pear.bat and change

	include_path="%PHP_PEAR_INSTALL_DIR%"

to

	"include_path='%PHP_PEAR_INSTALL_DIR%'"

## Timezone

PHP Warning: date_default_timezone_get(): It is not safe to rely on the system's timezone settings.

	sudo vim /etc/php5/cli/php.ini

Change

	date.timezone = America/Sao_Paulo
