# Network

Set static IP address

```bash
vim /etc/network/interfaces

# The primary network interface
auto eth0
iface eth0 inet static
	address 192.168.1.10
	netmask 255.255.255.0
	gateway 192.168.1.1
	dns-nameservers 8.8.8.8 8.8.4.4

sudo ifdown eth0 && sudo ifup eth0
```

```bash
vim /etc/resolvconf/resolv.conf.d/base

nameserver 8.8.8.8
nameserver 8.8.4.4

resolvconf -u

cat /etc/resolv.conf
```

Uninstall the dhcp client (otherwise it will overwrite our changes on the next renew cycle)

```bash
apt-get remove isc-dhcp-client -y
```

Restart network service (Ubuntu Server)

```bash
sudo ifdown eth0 && sudo ifup eth0
```
