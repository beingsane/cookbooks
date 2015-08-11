# Sinopia

## Ubuntu

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.25.4/install.sh | bash
su - $USER
nvm install stable
nvm use stable
nvm alias default stable
```

```bash
npm install -g sinopia
```

```bash
sinopia --listen 0.0.0.0:4873
```

## Configuration

### Config

```bash
npm set registry http://0.0.0.0:4873
npm set always-auth true
```

### User

```bash
npm adduser --registry http://0.0.0.0:4873
```

```bash
npm login
```

### Project

#### package.json

```json
[...]
"publishConfig": {
  "registry": "http://0.0.0.0:4873"
}
[...]
```

#### .npmrc

```bash
touch .npmrc
```

```ini
registry = http://0.0.0.0:4873
```
