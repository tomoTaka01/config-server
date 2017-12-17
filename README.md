## Spring Boot Sample
  * As of Spring Boot Version 2.0.0.M7(2017-12-17)
  * Cloud Config Server Sample
  * config files location is ${HOME}/config-sample(see the repository config-sample)

  * to see the config value for app-config-{local,prod}
```
http://localhost:8888/app-config/local
http://localhost:8888/app-config/prod
```

  * to see the config value for app-api-{local,prod}
```
http://localhost:8888/app-api/local
http://localhost:8888/app-api/prod
```

  * config file should be in the git directory

```
config-sample
├── app-api-local.yml
├── app-api-prod.yml
├── app-api.yml
├── app-config-local.yml
├── app-config-prod.yml
└── app-config.yml
```
