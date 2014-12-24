# SSH

Register hosts

```bash
cd C:\Users\<username>\.ssh

touch config

Host <hostname>
    HostName <ipaddress>
    Port <port>
    User <username>

ssh <hostname>
```

Access SSH using authorized key

```bash
cat C:\Users\<username>\.ssh\id_rsa.pub

ssh <hostname>

vim $HOME/.ssh/authorized_keys
```
