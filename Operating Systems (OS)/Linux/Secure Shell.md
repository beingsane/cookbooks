# Secure Shell

```bash
sudo apt-get install openssh-client
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
