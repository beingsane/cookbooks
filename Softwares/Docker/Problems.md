# Errors

**WARNING: No swap limit support**

```bash
docker info
sudo vim /etc/default/grub

GRUB_CMDLINE_LINUX="cgroup_enable=memory swapaccount=1"

sudo update-grub
sudo shutdown -r now
```

**Post http:///var/run/docker.sock/images/create?fromImage=nginx&tag=: dial unix /var/run/docker.sock: permission denied**

Add the docker group if it doesn't already exist:

```bash
sudo groupadd docker
```

Add the connected user "${USER}" to the docker group. You may have to logout and log back in again for this to take effect:

```bash
sudo gpasswd -a ${USER} docker
```

Restart the Docker daemon:

```bash
sudo service docker restart
```

Reload user session:

```bash
su - $USER
```

**Post http:///var/run/docker.sock/v1.19/containers/create: dial unix /var/run/docker.sock: no such file or directory. Are you trying to connect to a TLS-enabled daemon without TLS?**

```bash
$(boot2docker shellinit)
```

**Get http:///var/run/docker.sock/v1.19/images/json: dial unix /var/run/docker.sock: no such file or directory. Are you trying to connect to a TLS-enabled daemon without TLS?**

```bash
$(boot2docker up)
```
