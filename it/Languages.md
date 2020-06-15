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

- `mercateo# mvn install -am -pl trex.agent.catalog.management -DskipTests`

## JavaScript

- [yarn](https://classic.yarnpkg.com/lang/en/):package manager built by fb, Google, Exponent & Tilde
  - code is shared through package (~module) = code + package.json
  - package.json: ~metadata to the project
  - ~ alias for `npm run`

### Tesing

- [jest](https://jestjs.io/)

### node.js

- JavaScript runtime environment, executes JavaScript outside of a browser
- [nvm - Node Version Manager](https://github.com/nvm-sh/nvm): multiple node.js versions with default
- [npm](https://www.npmjs.com/): node package manager, yarn alternative

## Python

- [pyenv](https://github.com/pyenv/pyenv)
  - switch between multiple python versions (e.g. 2.7, 3.8...)
- [venv](https://docs.python.org/3/library/venv.html)
  - to manage different virtual environments (install different packages) of a single python version
  - only works for Python3.3+

- [wtfpython](https://github.com/satwikkansal/wtfpython)
- [urldecode](https://dev.to/k4ml/python-urldecode-on-command-line-2ek9)
