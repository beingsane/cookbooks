# OS X

### [Installation](https://echo.co/blog/os-x-1010-yosemite-local-development-environment-apache-php-and-mysql-homebrew)

```bash
sudo launchctl unload /System/Library/LaunchDaemons/org.apache.httpd.plist 2>/dev/null
```

```bash
brew tap homebrew/dupes
```

```bash
brew install -v homebrew/apache/httpd22 --with-brewed-openssl --with-mpm-event
```

```bash
brew install -v homebrew/apache/mod_fastcgi --with-brewed-httpd22
```

```bash
sed -i '' '/fastcgi_module/d' $(brew --prefix)/etc/apache2/2.2/httpd.conf
```

```bash
(export USERHOME=$(dscl . -read /Users/`whoami` NFSHomeDirectory | awk -F"\: " '{print $2}') ; export MODFASTCGIPREFIX=$(brew --prefix mod_fastcgi) ; cat >> $(brew --prefix)/etc/apache2/2.2/httpd.conf <<EOF
 
# Echo & Co. changes
 
# Load PHP-FPM via mod_fastcgi
LoadModule fastcgi_module    ${MODFASTCGIPREFIX}/libexec/mod_fastcgi.so
 
<IfModule fastcgi_module>
  FastCgiConfig -maxClassProcesses 1 -idle-timeout 1500
 
  # Prevent accessing FastCGI alias paths directly
  <LocationMatch "^/fastcgi">
    <IfModule mod_authz_core.c>
      Require env REDIRECT_STATUS
    </IfModule>
    <IfModule !mod_authz_core.c>
      Order Deny,Allow
      Deny from All
      Allow from env=REDIRECT_STATUS
    </IfModule>
  </LocationMatch>
 
  FastCgiExternalServer /php-fpm -host 127.0.0.1:9000 -pass-header Authorization -idle-timeout 1500
  ScriptAlias /fastcgiphp /php-fpm
  Action php-fastcgi /fastcgiphp
 
  # Send PHP extensions to PHP-FPM
  AddHandler php-fastcgi .php
 
  # PHP options
  AddType text/html .php
  AddType application/x-httpd-php .php
  DirectoryIndex index.php index.html
</IfModule>
 
# Include our VirtualHosts
Include ${USERHOME}/Sites/httpd-vhosts.conf
EOF
)
```

```bash
mkdir -pv ~/Sites/{logs,ssl}
```

```bash
touch ~/Sites/httpd-vhosts.conf
```

```bash
(export USERHOME=$(dscl . -read /Users/`whoami` NFSHomeDirectory | awk -F"\: " '{print $2}') ; cat > ~/Sites/httpd-vhosts.conf <<EOF
#
# Listening ports.
#
#Listen 8080  # defined in main httpd.conf
Listen 8443
 
#
# Use name-based virtual hosting.
#
NameVirtualHost *:8080
NameVirtualHost *:8443
 
#
# Set up permissions for VirtualHosts in ~/Sites
#
<Directory "${USERHOME}/Sites">
    Options Indexes FollowSymLinks MultiViews
    AllowOverride All
    <IfModule mod_authz_core.c>
        Require all granted
    </IfModule>
    <IfModule !mod_authz_core.c>
        Order allow,deny
        Allow from all
    </IfModule>
</Directory>
 
# For http://localhost in the users' Sites folder
<VirtualHost _default_:8080>
    ServerName localhost
    DocumentRoot "${USERHOME}/Sites"
</VirtualHost>
<VirtualHost _default_:8443>
    ServerName localhost
    Include "${USERHOME}/Sites/ssl/ssl-shared-cert.inc"
    DocumentRoot "${USERHOME}/Sites"
</VirtualHost>
 
#
# VirtualHosts
#
 
## Manual VirtualHost template for HTTP and HTTPS
#<VirtualHost *:8080>
#  ServerName project.dev
#  CustomLog "${USERHOME}/Sites/logs/project.dev-access_log" combined
#  ErrorLog "${USERHOME}/Sites/logs/project.dev-error_log"
#  DocumentRoot "${USERHOME}/Sites/project.dev"
#</VirtualHost>
#<VirtualHost *:8443>
#  ServerName project.dev
#  Include "${USERHOME}/Sites/ssl/ssl-shared-cert.inc"
#  CustomLog "${USERHOME}/Sites/logs/project.dev-access_log" combined
#  ErrorLog "${USERHOME}/Sites/logs/project.dev-error_log"
#  DocumentRoot "${USERHOME}/Sites/project.dev"
#</VirtualHost>
 
#
# Automatic VirtualHosts
#
# A directory at ${USERHOME}/Sites/webroot can be accessed at http://webroot.dev
# In Drupal, uncomment the line with: RewriteBase /
#
 
# This log format will display the per-virtual-host as the first field followed by a typical log line
LogFormat "%V %h %l %u %t \"%r\" %>s %b \"%{Referer}i\" \"%{User-Agent}i\"" combinedmassvhost
 
# Auto-VirtualHosts with .dev
<VirtualHost *:8080>
  ServerName dev
  ServerAlias *.dev
 
  CustomLog "${USERHOME}/Sites/logs/dev-access_log" combinedmassvhost
  ErrorLog "${USERHOME}/Sites/logs/dev-error_log"
 
  VirtualDocumentRoot ${USERHOME}/Sites/%-2+
</VirtualHost>
<VirtualHost *:8443>
  ServerName dev
  ServerAlias *.dev
  Include "${USERHOME}/Sites/ssl/ssl-shared-cert.inc"
 
  CustomLog "${USERHOME}/Sites/logs/dev-access_log" combinedmassvhost
  ErrorLog "${USERHOME}/Sites/logs/dev-error_log"
 
  VirtualDocumentRoot ${USERHOME}/Sites/%-2+
</VirtualHost>
EOF
)
```

```bash
(export USERHOME=$(dscl . -read /Users/`whoami` NFSHomeDirectory | awk -F"\: " '{print $2}') ; cat > ~/Sites/ssl/ssl-shared-cert.inc <<EOF
SSLEngine On
SSLProtocol all -SSLv2 -SSLv3
SSLCipherSuite ALL:!ADH:!EXPORT:!SSLv2:RC4+RSA:+HIGH:+MEDIUM:+LOW
SSLCertificateFile "${USERHOME}/Sites/ssl/selfsigned.crt"
SSLCertificateKeyFile "${USERHOME}/Sites/ssl/private.key"
EOF
)
```

```bash
openssl req \
  -new \
  -newkey rsa:2048 \
  -days 3650 \
  -nodes \
  -x509 \
  -subj "/C=US/ST=State/L=City/O=Organization/OU=$(whoami)/CN=*.dev" \
  -keyout ~/Sites/ssl/private.key \
  -out ~/Sites/ssl/selfsigned.crt
```

```bash
brew services start httpd22
```

```bash
sudo bash -c 'export TAB=$'"'"'\t'"'"'
cat > /Library/LaunchDaemons/co.echo.httpdfwd.plist <<EOF
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
<plist version="1.0">
<dict>
${TAB}<key>Label</key>
${TAB}<string>co.echo.httpdfwd</string>
${TAB}<key>ProgramArguments</key>
${TAB}<array>
${TAB}${TAB}<string>sh</string>
${TAB}${TAB}<string>-c</string>
${TAB}${TAB}<string>echo "rdr pass proto tcp from any to any port {80,8080} -> 127.0.0.1 port 8080" | pfctl -a "com.apple/260.HttpFwdFirewall" -Ef - &amp;&amp; echo "rdr pass proto tcp from any to any port {443,8443} -> 127.0.0.1 port 8443" | pfctl -a "com.apple/261.HttpFwdFirewall" -Ef - &amp;&amp; sysctl -w net.inet.ip.forwarding=1</string>
${TAB}</array>
${TAB}<key>RunAtLoad</key>
${TAB}<true/>
${TAB}<key>UserName</key>
${TAB}<string>root</string>
</dict>
</plist>
EOF'
```

```bash
sudo launchctl load -Fw /Library/LaunchDaemons/co.echo.httpdfwd.plist
```
