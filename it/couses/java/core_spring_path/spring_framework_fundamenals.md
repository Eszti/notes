# Spring Framework: Spring Fundamentals

## What is Spring

- started as
  - IoC container
  - DI
  - without using EJB (enterprise java beans)

- can be used with or without JEE
- POJO (plain old java object) based
- unobtrusive
- AOP & Proxies: code is smaller
- best practice

- the problems
  - testability
  - maintainability
  - scalability
  - complexity
  - business focus
- the solutions
  - configuration
  - focues
  - testing
  - annotation & xml based
  - interface based
- how it works
  - POJOS
  - HashMap
  - Registry

## Architecture and Project Setup

- WORA: writre once, run everywhere
- spring cannet be downloaded standalone, only via maven or gradle
- configuration
  - makes things brittle
  - difficulties in testing
- spring configuration options
  - java config
    - not to mix code with xml
    - no context file
    - everything available
    - ~ POJO AppConfig, get from main
    - configuration annotations
      - @Configuration
      - @Bean
        - to get intances of beans
        - instances of a repository
        - singletons
    - setter injection
      - calling a setter on a bean
    - constructor injection
      - using the ctor
  - annotations
  - xml config
- get spring into our application
  - maven dependency

## Scopes and Autowiring

- 5 scoopes
  - everywhere
    - singletion
      - default
      - one instatiation
      - one instance / spring container (~application context)
      - @Scope( value = BeanDefinition.SCOPE_SINGLETON)
    - prototype
      - unique instance per request
      - opposition of singleton
  - only in web-aware projects
    - request
      - bean per HTTP request (more than prototype)
    - session
      - bean per HTTP session (more than request)
    - global
      - bean per application (more than session)
  - scope can be defined at method or class level

- autowiring
  - convention over configuration
  - @Autowired
    - e.g. no args ctor + setter

- Stereotypes Annotations
  - @Bean
    - only at method level, not on class!
  - @Component
    - basically the same as @Bean
  - @Repository
    - classes being used as repositories
  - @Service
    - where you put your business logic
    - not a web or microservices
  - @Controller
    - web or microservice
  - do on the implementation
- @Configuration
- @ComponentScan

## Spring Configuration using XML

- why
  - first approach
  - simplier
  - separation of concerns
- features
  - applicationContext.xml: conventional name
  - ~ HashMap
  - can simply be a registry
  - namespaces can help

- bean definition
  - XML declaration
    - just classes
    - replaces keyword new
    - define class but use the interface
    - attributes
      - name
      - class
    - properties (setter injection)
      - name
      - ref
    - constructor-arg (ctor injection)
      - index
      - ref
  - main
    - new ClasspathXmlApplicationContext
    - appContext.getBean
  - ctor injection
    - (+) guaranteed contract
    - (-) constructor for each setup
    - can be used together

- autowires
  - byType
    - if only one instance, if multiple exist: fatal error
    - setter injection
  - byName
    - can choose which one
    - if a bean has a "master" property (and a "setMaster" method), Spring will look for a beasn named "master"
    - setter injection
  - constructor
    - analogous to byType
    - If there is not exactly one bean of the constructor argument type in the container, a fatal error is raised
    - ctor injection
  - no
    - bean references must be defined by ref elements

## Advanced Bean Configuration

- Bean Lifecycle
  - @PostConstruct (javax annotiation)
    - do not open & close connection
    - should be used for extra configs

- FactoryBean
  - builds on the factory method pattern
  - enforce a contract
  - configure objects without constructor

- SpEL: Spring Expression Language
  - use cases
    - manipulate object graph
    - evaluate at runtime
    - evaluate & manipulate your config
  - @Value
    - seed value in compile time to code

- AOP Proxies
  - not to modify your code
  - profiles
    - adapt environments
    - runtime configurations
      - e.g. separate dev from prod
    - @Profile("dev")
