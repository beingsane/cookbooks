## Block Files

Deny access to extension xml files

```ini
<Files ~ "\.xml$">
	Order allow,deny
	Deny from all
	Satisfy all
</Files>
```

Allow access to extension xml files

```ini
<Files ~ "\.xml$">
	Order allow,deny
	Allow from all
	Satisfy all
</Files>
```

Sitemap

```ini
<FilesMatch "(?!sitemap)\.xml$">
	Order allow,deny
	Deny from all
	Satisfy all
</Files>
```
