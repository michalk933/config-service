How to make server configuration
====================

### 1.Add dependency
```xml
<dependency>
  <groupId>org.springframework.cloud</groupId>
  <artifactId>spring-cloud-config-server</artifactId>
</dependency>
```

### 2.Add annotation to run class
```java
@EnableConfigServer
```

### 3.Add to application.properties info where are file configuration for other microservces.
This is link to place where is dir with application.properties files.
You must make “git init” in this dir. When you change file you must make 2 commond:
git add .
git commit -m “you description changes”
```java
spring.cloud.config.server.git.uri=${HOME}/Desktop/config
```

### 4.And add block security for simply test.
```java
management.security.enabled=false
```

### 5.Every microservice add
```java
spring.application.name=eureka-service
spring.cloud.config.uri=http://localhost:8888
```
