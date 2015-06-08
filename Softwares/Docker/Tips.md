# Tips

##### Get current docker IP via command line

Open [Kitematic](https://kitematic.com/), click on `Docker CLI`:

```bash
docker-machine env dev

export DOCKER_TLS_VERIFY=1
export DOCKER_CERT_PATH="/Users/[username]/.docker/machine/machines/dev"
export DOCKER_HOST=tcp://192.168.99.100:2376

eval "$(docker-machine env dev)"
```
