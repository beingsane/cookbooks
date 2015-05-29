# Proxy configurations

#### List configurations

```bash
npm config list
```

#### Set registry URL

```bash
npm config set registry http://registry.npmjs.org/
```

#### Set proxy

```bash
npm config set http-proxy http://username:password@ip:port
npm config set https-proxy http://username:password@ip:port
```

Remove proxy

```bash	
npm config delete http-proxy
npm config delete https-proxy
```

#### SSL

```bash	
npm set strict-ssl false
```
