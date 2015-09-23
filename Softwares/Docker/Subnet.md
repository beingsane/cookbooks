# Subnet

## Change Docker subnet

```bash
sudo service docker stop
```

```bash
iptables -t nat -F POSTROUTING
```

```bash
ip link set dev docker0 down
ip addr del 172.17.42.1/16 dev docker0
```

```bash
ip addr add 192.168.10.1/24 dev docker0
ip link set dev docker0 up
```

```bash
ip addr show docker0
```

```bash
sudo service docker start
```

```bash
iptables -t nat -L -n
```
