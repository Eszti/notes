# Architecture

## Documentation

- [Diagrams](https://diagrams.mingrammer.com/): for cloud system architectures

## API to services

- [blog](https://nordicapis.com/building-a-backend-for-frontend-shim-for-your-microservices/)
- Classical Approach
  - one general API
- Microservice Design
  - each application client type has its own dedicated API
  - lots of duplications
- Backend for Frontend (BFF)
  - use shims for translation services

## BDD: Behaviour Driven Development

- [Cucumber](https://cucumber.io/)
  - Gherkin: language parser
  - describe software behaviour with logical language
  - enables automatic acceptance tests

## DDD: Domain Driven Development

- situation: scrum team (implementation) ---- stakeholders + domain experte (context & details)
- official book: 2004
- Domains
  - problem space (=analysis): subdomains
    - core subdomain: use DDD (difficult tasks)
    - supporting subdomain (simpler solutions, probably jsut CRUD)
    - generic subdomain: e.g. accounting, just buy
  - solution space (=design & implementation): bounded context, ~IT-teams
- Model
  - Analysis model: domain, only in theory
  - code model: is The Model  -> Model Driven Development
  - ubiquitous language: common language between stakeholders & developers (e.g product - with special meaning)
  - knowledge crunching: **evnet sourcing** domain events
    - ~ domain model, start with a kick-off workshop, than iterate, use these event for communication
- Bounded context
  - own ubi.lang. & model
  - decompose it to **business components** and **components**
  - ~ microservices
- application architecture
  - onion model: domain layer (~api) -> application service (use case services with interfaces) -> dependencies (with injection)
- context map: relationship between BCs
  - e.g. how to translate ubi.lang.
  - patterns: shared kernel, conformist, anticorruption, open host service...
  - connenting BC: RPC, REST, FTP, Commands & Events, Message Broker (sync or async)
  - **eventual consistency** instead of *transactional consistency* (roll-forward instead of roll-back)
- tactical patterns
  - Value objects: immutable, technical lifecycle (e.g. MonetaryAmount) -> can be an Entity in anouther domain
  - Entity: domain model lifecycle, ID (e.g. Invoice)
  - Domain Service: behaviour, stateless
  - Domain events: historical records, immutable
  - Aggregate: tree of domain objects (entity & value objects) with ID reference
