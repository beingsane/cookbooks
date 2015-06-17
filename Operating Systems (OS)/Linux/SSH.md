# SSH

```bash
sudo apt-get install openssh-client
sudo apt-get install openssh-server
```

```bash
sudo service ssh start
```

Speed up SSH login

```bash
vim /etc/ssh/sshd_config

UseDNS no

service ssh restart
```
