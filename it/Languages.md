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

## C-sharp

- CLR: common language runtine
- IL: intermediate language
- Linq: Language-Integrated Query
- property
  - public string Name { get; set; }
- WPF: data binding

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

### Testing

- [mockito][(https://github.com/mockito/mockito)
  - 2.0: opt-in mocking for final classes/methods
    - src/test/resources/mockito-extensions/org.mockito.plugins.MockMaker: `mock-maker-inline`


### Validation

- [Hibernate Validator](https://docs.jboss.org/hibernate/validator/5.4/reference/en-US/html_single/#validator-gettingstarted-createmodel)

### Maven

- build automation: how & dependencies
- POM: project object model
  - parent-pom
- plugin-based, all work is done by plugins
- dependencies
  - snapshots

### Logging

- [slf4j](http://www.slf4j.org/)
  - facade for logging
- [log4j](https://logging.apache.org/log4j/2.x/)
  - logging framework
- [logback](http://logback.qos.ch/)
  - logging framework

## Python

### Environment

- [pyenv](https://github.com/pyenv/pyenv)
  - manage different versions and virtual environments
  - `pyenv install 3.8.3`
  - `pyenv uninstall 3.8.3`
  - `pyenv global 3.8.3`
- [venv](https://docs.python.org/3/library/venv.html)
  - to manage different virtual environments (install different packages) of a single python version
    - `python -m venv ./venv`
    - `source ./venv/bin/activate`
  - only works for Python3.3+

### Dependencies

- to list dependencies
  - `pip freeze`
- requirements 
  - store in `requirements.txt`
  - install with `pip install -r requirements.txt`

### Package managers

#### pip

- [pip](https://pypi.org/project/pip/)
- to delete all dependencies
  - `pip freeze | xargs pip uninstall -y`

#### conda

- [conda](https://docs.conda.io/en/latest/)

### Build distribution formats

- egg
  - introduced by setuptools
- wheel
  - introduced by PEP (Python Enhancement Proposal)
  - supported by pip
  - currently standard for build and binary packaging

### Bibs

- [jinja](https://jinja.palletsprojects.com/en/2.11.x/)
  - web template language
  - can also generate markup and source code
- [flask](https://flask.palletsprojects.com/en/1.1.x/)
  - simple web framework
  - no  database abstraction layer, nor form validation...

### Useful

- [wtfpython](https://github.com/satwikkansal/wtfpython)
- [urldecode](https://dev.to/k4ml/python-urldecode-on-command-line-2ek9)

## Typescript

- will be compiled to javascript
- type check only at compiler time
- structural comparison (talk like a duck, looks like a duck...)
- any can always be used

## Regex

```bash
^((?!word).)*$    # does not contian work
.*word-*          # contains word
```
