## Spring Boot Sample
  * As of Spring Boot Version 2.0.0.M7(2017-12-22)
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

  * config values
    * app-config-{local,prod}.yml

| |default|local|prod|
|:---|:---|:---|:---|
|config-key1|val1-default|-|-|
|config-key2|val2-default|val2-local|-|
|config-key3|val3-default|-|val3-prod|

  * config values
    * app-api-{local,prod}.yml

| |default|local|prod|
|:---|:---|:---|:---|
|retry-cout|1|-|-|
|api-name|N/A|ロカール用ＡＰＩ名|本番用ＡＰＩ名|

  * gradle seting for config server

```
dependencies {
  compile('org.springframework.cloud:spring-cloud-config-server')
}
```

  * you need 2 file
    * application.yml
```
server:
  port: 8888
spring:
  cloud:
    config:
      server:
        git:
          uri: file:${HOME}/config-sample
```

    * CconfigServerApplication.java
```Java
@EnableConfigServer
@SpringBootApplication
public class ConfigServerApplication {
  public static void main(String[] args) {
    SpringApplication.run(ConfigServerApplication.class, args);
  }
}
```

  * to seee the result 
  http://tomotaka.hatenablog.com/entry/2017/12/22/074740

