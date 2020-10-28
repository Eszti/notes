# Spring: The Big Picture

## What is Spring

- What is spring?
  - most popular java framework
  - entire family of projects
  - Spring ecosystem

- Spring Framework
  - moving complexitiy of Java EE
  - removing boiler plate code
  - several projects
    - Spring Security
    - Spring Data
    - upon them: Spring Boot
      - game changer
      - autoconfiguration
      - simple
    - upon: Spring Cloud
      - microservices

- why spring
  - much more than alternative of Java EE
  - make SW development easier
  - flexible
  - large & active community
  - open source but backed by a company (Pivotal)

## Spring with Spring Boot

- easy but not lack of features (fully features!)
- built on top of the Spring Framework
- for web and non-web

- auto-configuration
  - based on context
  - e.g. assuption you have a DB -> auto-setup
  - easlily be en-/disabled
- standalone
  - typical process for web application
    - package, download webserver, configure webserver, deploy & start webserver
    - java -jar my-app.jar: package & run
- opinionated
  - not a bad thing!
  - lots of decisions
  - choices are made, focus on development
  - start.spring.io
    - generate spring boot application

## Understanding Spring's Foundations: The Spring Framework

- Spring Framework
  - software framework
  - universal, reusable
  - provides particular functionality
  - part of a larger software platform (java)
  - facilitate development

- Spring Framework
  - started with Spring
  - later: Spring Projects (e.g. Spring Boot)
  - modular
    - Core
      - foundation module
      - i18n
      - validation
      - data binding
      - type conversion
      - center: dependency injection
        - fulfill dependencies
          - fulfill our own (tightly coupled)
          - declare our dependencies (loosely coupled)
    - Web
      - handling web request
        - Web MVC
          - based on Servlet API
            - object that receives a request and generates a response
            - low level
          - Model-View-Controller
        - Web Webflux
          - uses reactive programming
            - stream of data and reactions
          - async
    - AOP
      - Acpect-oriented Programming
        - programming paradigm
        - increases modularity
        - separation of cross-cutting concerns (e.g. security)
      - implementation of AOP
      - represented as metadata (~annotations)
    - Data Access
      - e.g. JDBC boilder plate code
      - @Transactional
      - exception translation
        - data integrity violation excpetion (different code for MySQL, Oracle...)
      - easy config for testing
    - Integration
      - make different systems work together
      - provide access
        - RMI
        - messaging
        - web services
          - e.g. REST: @RestController, @GetMapping, @PathVariable
      - invoke
        - e.g. REST: getForObject
    - Testing
      - exploits DI
      - unit testing
        - mocking (pre-written mocks)
      - integration testing
        - individual modules are combined
        - common testing scenarios
        - cleanup

## Exploring Other Spring Projects

### Spring Data

- [doc](https://spring.io/projects/spring-data)
- ~ Spring Framework Data Access
- support for many different types
- main modules
  - REEST, JPA, JDBC, KeyValue, LDAP ...
- community modules
  - DynamoDB, Elasticsearch ...

### Spring Cloud

- [doc](https://spring.io/projects/spring-cloud)
- to build distributed systems
  - microservices
    - single-purpose domain
    - solves common problems, e.g. service discovering
- umbrella project for lots of specific projects

### Spring Security

- [doc](https://spring.io/projects/spring-security)
- authentication
- authorisation
- protection against attacks

## Is Spring a good fit

- advantage
  - rock-solid & well engineered
  - stood the test of time
  - huge community
  - well liked
  - large talent pool
  - wealth of existing knowledge
  - good docu
  - actively developed
  - built-in IDE support
  - scalable
- drawbacks
  - too much magic (annotations...)
  - steep learning curve
  - increase the size of your deliverable
  - hard to debug (hides a lot of details)
  - memory overhead
  - too complex --> Spring Boot
  - too configurable
  - big, only for long-living, complex applications
