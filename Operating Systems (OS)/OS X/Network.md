# Network

##### Listen TCP

```bash
sudo lsof -i -n -P | grep TCP

lsof -i | grep LISTEN

lsof -i 4 -a
```

##### Kill TCP

```bash
sudo lsof -i :5955

sudo kill -9 PID # add the PID number
```
