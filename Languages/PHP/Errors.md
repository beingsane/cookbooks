# Errors

## Generic

PHP Fatal error:  Call to undefined function ..\file()

```bash
extension=php_fileinfo.dll
```

PHP Fatal error:  Call to undefined function ..\mb_strtolower()

```bash
extension=php_mbstring.dll
```

## PEAR

PEAR ERROR: Syntax Error, unexpected '(' in Unknown on Line 14

Open pear.bat and change

```bash
include_path="%PHP_PEAR_INSTALL_DIR%"
```

to

```bash
"include_path='%PHP_PEAR_INSTALL_DIR%'"
```

## Timezone

PHP Warning: date_default_timezone_get(): It is not safe to rely on the system's timezone settings.

```bash
vim /etc/php5/cli/php.ini
date.timezone = America/Sao_Paulo
```
