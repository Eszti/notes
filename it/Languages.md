# Languages

## C++

### C++20

- modules
  - no more #inluce
  - export & import
  - faster compiliation, no more .h/.cpp
- concepts
  - requires(): compiler feature with static_assert, constraints for templates
  - conceipts: complie time predicate, template definition (e.g. what behaves like a boolean)
- ranges
  - a conceopt
  - e.g. sort without .begin() & .end()
  - views: requirements of a range with O(1) copy/move/assignment operations
  - pipes: applicable for unary adopters
- coroutines
  - co_yield, co_return, co_await
  - 2 types: with & w/o stack
  - e.g. for generators, lazy evaluation, event driven programming
- lambdas (since C++11)
  - default initialisation, can be members

## Java

- [sdkman](https://sdkman.io/install): multiple sdk version (e.g. java)

### Command line

- jar -tf *jar_file*: lists all classes in jar

### Spring

- Spring Framework
  - features, e.g.
    - dependency injection
    - mvc
    - jdbc...
- Spring Boot
  - eliminate boilerplate from Spring configuration, e.g.
    - server
    - deployment...

### Concepts

- POJO: plain old java object: ordinary java object
- JavaBean: classes, encapsulate many objects, servializable, no-arg ctor, have getter & setter, used as standard

### Important libraries

- [Dataprovider](https://github.com/TNG/junit-dataprovider) by TNG

### Code snippets

``` java
    // Test with exception:
    // when
    ThrowingCallable callable = () -> uut.doSomething(a, b);

    // then
    assertThatCode(callable)
        .isInstanceOf(ExpectedException.class)
        .hasMessage("Object " + id + " does not exist. Or whatever");
```

### Validation

- [Hibernate Validator](https://docs.jboss.org/hibernate/validator/5.4/reference/en-US/html_single/#validator-gettingstarted-createmodel)

### Maven

- build automation: how & dependencies
- POM: project object model
  - parent-pom
- plugin-based, all word is done by plugins
- dependencies
  - snapshots

- `mercateo# mvn install -am -pl trex.agent.catalog.management -DskipTests`

## Python

- [pyenv](https://github.com/pyenv/pyenv)
  - switch between multiple python versions (e.g. 2.7, 3.8...)
- [venv](https://docs.python.org/3/library/venv.html)
  - to manage different virtual environments (install different packages) of a single python version
  - only works for Python3.3+

- [wtfpython](https://github.com/satwikkansal/wtfpython)
- [urldecode](https://dev.to/k4ml/python-urldecode-on-command-line-2ek9)
