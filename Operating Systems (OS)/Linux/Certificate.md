# Certificate

#### Installing a root/CA Certificate

Given a CA certificate file 'foo.crt', follow these steps to install it on Ubuntu:

1. Create a directory for extra CA certificates in /usr/share/ca-certificates

	```bash
	sudo mkdir /usr/share/ca-certificates/extra
	```

2. Copy the '.crt' file to the directory

	```bash
	sudo cp foo.crt /usr/share/ca-certificates/extra/foo.crt
	```

3. Let Ubuntu add the '.crt' file's path relative to /usr/share/ca-certificates to /etc/ca-certificates.conf

	```bash
	sudo dpkg-reconfigure ca-certificates
	```
