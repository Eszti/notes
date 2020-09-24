# Architecture

## Documentation

- [Diagrams](https://diagrams.mingrammer.com/): for cloud system architectures

## Testen

- [ArchUnit](https://www.archunit.org/)
  - TNG open source
  - rule definition and evaluation
  - pre-defined structures: layer & onion

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

- situation: **scrum team** (implementation) ---- **stakeholders + domain experte** (context & details)
- official book: 2004
- Domains
  - **problem space** (=analysis): subdomains
    - core subdomain: use DDD (difficult tasks)
    - supporting subdomain (simpler solutions, probably jsut CRUD)
    - generic subdomain: e.g. accounting, just buy
  - **solution space** (=design & implementation): **bounded context**, ~IT-teams
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

## REST-API Design

- REpresentational State Transfer
- Restful: REST implementation
- Maturity levels (level 1-3)
  - level 1: Resouces
    - resource ~ object
    - communicaton with repesentations
    - can be identified with an URIs (URL + URN)
    - best practice: plural
  - level 2: HTTP Verbs
    - POST, GET, PUT (overwrite), PATCH (only parts), DDELETE
    - Statuscodes
      - 2xx: OK / 201 (created), 204 (no content)
      - 3xx: forward
      - 4xx: Client error / 401 (not authorized = not authenticated), 403 (forbidden), 404 (not found)
      - 5xx: server error / 500 (server error)
    - HTTP header
      - content-type: of payload
      - accept: what the client accepts
      - MIME-types: can be customized (vnd.aaa.bbb.v1+json)
  - level 3: links (HATEOS)
    - HAL: a standard
    - to header
    - json hyperschema
    - access control, flow, changable API
    - OPTIONS request: which calls are available
    - con: loads of requests
- versioning
  - MIME type
  - path: v1/
  - header
  - through links (HATEOS)
- RAML: RESTful API Modeling Language, YAML-based, for describing RESTful APIs
