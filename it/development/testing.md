# Testing

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