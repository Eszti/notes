# Java

## Version manager

- [sdkman](https://sdkman.io/install): multiple sdk version (e.g. java 8 and 11...)

## Concepts

- POJO: plain old java object: ordinary java object
- JavaBean: classes, encapsulate many objects, servializable, no-arg ctor, have getter & setter, used as standard

## Best practices

- general tutorials from [eugenp|https://github.com/eugenp/tutorials/tree/master/core-java-modules]
- Validation
  - [Hibernate Validator](https://docs.jboss.org/hibernate/validator/5.4/reference/en-US
  /html_single/#validator-gettingstarted-createmodel)
- Regex
  - use matcher from compiled pattern, described [here](https://www.baeldung.com/java-regex-pre-compile)
- REST framework	
  - [Jersey](https://github.com/eclipse-ee4j/jersey)

## Useful

``` java
    // Test with exception:
    // when
    ThrowingCallable callable = () -> uut.doSomething(a, b);

    // then
    assertThatCode(callable)
        .isInstanceOf(ExpectedException.class)
        .hasMessage("Object " + id + " does not exist. Or whatever");
```

```bash
# lists all classes in jar
- jar -tf *jar_file*
```

## Spring

### Spring Framework

- features, e.g.
  - dependency injection
  - mvc
  - jdbc...

### Spring Boot

- extension of Spring
- eliminate boilerplate from Spring configuration
- convention over configuration
- simplifies deployment

#### Features

- automatic configuration
  - maven dependencies
- [starter dependencies](https://www.javatpoint.com/spring-boot-starters)
  - dependent libraries you need
  - spring-boot-starter-test has JUnit, Mockito, Spring core, Spring test...
  - spring-boot-starter-web has Spring MVC, REST, Tomcat, Jackson (json to java object)...
- spring boot CLI
  - prototyping
- actuator
  - for monitoring

#### Bootstrapping

- [spring initializr](https://start.spring.io/)
- alternatively you can you Spring Boot CLI
  - `spring init --dependencies=web,data-jpa app`
- auto configuration
  - `application.properties`
    - e.g. loglevel, database
  - @SpringBootApplication (3 in 1)
    - @SpringBootConfiguration
    - @EnableAutoConfiguration
    - @ComponentScan
  - @SpringBootTest
- profile
  - for different environments
  - `spring.profiles.active=dev`
  - `application-{profile}.properties`

#### Data Access

- H2
  - open source, in-memory database, written in Java
  - not production ready
  - web browser viewer
- ORM with JPA layers
  - persistence
    - data store
  - JDBS (Java Database Connectivity)
    - java API to cennect and execute queries
  - JPA (Java Persistence API)
    - abstraction, make mapping easier
    - no implementation, only interfaces
  - implementation / instance provider
    - Spring Data JPA (uses Hibernate)
  - @Entity, @Id, @GEneratedValue, @Column, @ManyToOne, @JoinColumn
  - `CrudRepository`...
    - implementation is provided by Spring Data JPA

#### Testing

- `spring-boot-starter-test`
- @SpringBootTest

#### Other modules

- MVC
  - `spring-boot-starter-web`
  - @Controller, @GetMapping
- RESTful
  - @RestController
  - response entities
  - response codes
- GraphQL
  - `graphql-spring-boot-starter`
  - `graphql-java-tools`
  - schema
- Monitoring
  - actuator
    - health, metrics...
    - custom health indicators

## Testing

- [Dataprovider](https://github.com/TNG/junit-dataprovider) by TNG
- [mockito][(https://github.com/mockito/mockito)
  - `@Mock`, `@Spy`
  - 2.0: opt-in mocking for final classes/methods
    - src/test/resources/mockito-extensions/org.mockito.plugins.MockMaker: `mock-maker-inline`
  - 3.0: openMocks() also closes resources

## Maven

- build automation: how & dependencies
- POM: project object model
  - parent-pom
- plugin-based, all work is done by plugins
- dependencies
  - snapshots

## Logging

- [slf4j](http://www.slf4j.org/)
  - facade for logging
- [log4j](https://logging.apache.org/log4j/2.x/)
  - logging framework
- [logback](http://logback.qos.ch/)
  - logging framework