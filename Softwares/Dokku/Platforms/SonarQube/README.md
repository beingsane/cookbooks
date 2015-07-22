# SonarQube

```bash
dokku postgresql:create sonarqube_production
dokku postgresql:link sonarqube sonarqube_production
dokku postgresql:info sonarqube sonarqube_production

dokku config:set sonarqube DB_HOST=postgresql \
DB_NAME=sonarqube_production \
DB_USER=sonarqube \
DB_PASS= # Run `dokku postgresql:info sonarqube sonarqube_production` to get password.
```
