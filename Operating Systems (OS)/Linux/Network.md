# Network

#### Set static IP address

```bash
sudo vim /etc/network/interfaces
```

```ini
# The primary network interface
auto eth0
iface eth0 inet static
	address 192.168.1.10
	netmask 255.255.255.0
	gateway 192.168.1.1
	dns-nameservers 8.8.8.8 8.8.4.4
```

```bash
sudo vim /etc/resolvconf/resolv.conf.d/base
```

```ini
nameserver 8.8.8.8
nameserver 8.8.4.4
```

```bash
sudo resolvconf -u

cat /etc/resolv.conf
```

Uninstall the dhcp client (otherwise it will overwrite our changes on the next renew cycle)

```bash
sudo apt-get remove isc-dhcp-client -y
```

```bash
sudo ifdown eth0 && sudo ifup eth0
```
