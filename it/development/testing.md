# Testing

## Maintainable Unit Tests

### Unit tests

- non-maintainable
- boundary testing
- test do not prove code
  - run as expected for certain input
  - value of tests: choosing values wisely
- Arrange - Act - Assert (given - when -then)
- try to stick to one naming convention
  - e.g. method-under-test_test-scenario_expected-behaviour
- test runners
  - try-catch and report
- test strategies
  - state testing
    - public vs visible for testing
    - gives the class more freedom to change 
  - interaction testing
    - via test doubles (derived classes with necessary properties)
    - never use implementation, only interfaces
    - use only when interaction is the requirement
- failing
  - nicely failed: failing asserting
  - ugly failed: because of an unrelated exception

### White box testing

- we have to code
- theories
	- path coverage
	- branch coverage (preferred)

### Managing dependencies

### Abstract Data Types (ADTs)

### Generic classes under test

### Testing interfaces

### Concepts under test

### Design by Contract

## Code Quality

### Continuous Code Improvement

#### [Rollbar](https://rollbar.com/)

- features
  - make errors visible
  - automated grouping with ML
  - trigger AI-assisted workflows
  - integrate to development process
    - link to the error in git (with blame)
    - create Jira ticket
    - slack notification
- concepts
  - project ~ 1 releasable item ~ 1 git repo
  - occurrence: events
  - item: grouped occurrences (using ML)
  - severity level ~ log level
- grouping is crucial
  - goal is: self-healing software
  
## Architecture testing

### [ArchUnit](https://www.archunit.org/)
  
- TNG open source
- rule definition and evaluation
- pre-defined structures: layer & onion
  
## Behaviour Driven Development

### [Cucumber](https://cucumber.io/)

- Gherkin: language parser
- describe software behaviour with logical language
- enables automatic acceptance tests