# Secure Shell (SSH)

#### Server

```bash
sudo apt-get install openssh-server
sudo service ssh start
```

Speed up SSH login

```bash
cat << EOF | sudo tee -a /etc/ssh/sshd_config
UseDNS no
EOF

sudo service ssh restart
```

#### Client

```bash
sudo apt-get install openssh-client
```

#### Login

```bash
cat ~/.ssh/id_rsa.pub | ssh user@ip "mkdir -p ~/.ssh && cat >>  ~/.ssh/authorized_keys"

ssh user@ip
```
