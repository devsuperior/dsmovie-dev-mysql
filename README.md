## Estudo de caso Spring Boot e MySQL

*Conectar um projeto Spring Boot ao MySQL*

#### Pré-requisito

[Utilizar Docker Compose com MySQL e phpMyAdmin](https://github.com/devsuperior/docker-compose-mysql)

[Baixar projeto DSMovie Ref](https://github.com/devsuperior/dsmovie-ref)

### Passo: Dependência Maven

- Incluir a dependência do mysql no arquivo pom.xml:

```xml
<dependency>
    <groupId>mysql</groupId>
    <artifactId>mysql-connector-java</artifactId>
    <scope>runtime</scope>
</dependency>
```

### Passo: Validação no MySQL local
- Criar o perfil de projeto: dev
- Gerar script SQL no perfil dev
- Testar projeto no banco MySQL local

#### application-dev.properties
```
#spring.jpa.properties.javax.persistence.schema-generation.create-source=metadata
#spring.jpa.properties.javax.persistence.schema-generation.scripts.action=create
#spring.jpa.properties.javax.persistence.schema-generation.scripts.create-target=create.sql
#spring.jpa.properties.hibernate.hbm2ddl.delimiter=;

spring.datasource.url=jdbc:mysql://localhost:3307/dsmovie?serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=1234567

spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect
spring.jpa.properties.hibernate.jdbc.lob.non_contextual_creation=true
spring.jpa.hibernate.ddl-auto=none
```



