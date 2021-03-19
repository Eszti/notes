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

- to cope with business complexity
- scrum team (implementation): one side
- stakeholders + domain experts (context & details): other side
- scrum emphasizes communications (from PO)
- problem
  - implementation does not suit customer value
- solution pieces
  - scrum
  - architecture
  - principles
  - strategic design
  - tactical design
- official book: 2004

### Knowledge Crunching

- recognize when it's bad
  - code always with workaround
  - refactoring takes long
  - domain are not recognisable
  - unique is not unique
- to determine business domains
  - business experts know them
  - developers need them

#### Domain Experts

- product mgm
- support teams
- developers
- CEO
- sales
- finance & legal

#### Rules

- start from use case (kick-off workshop)
  - methods
    - event storming
    - story telling
- ask questions
  - why are we building it? what if we don't build?
  - what is the business value?
- visualize
- event storming 
- iterate & evolve regularly
- given-when-then
- follow the money

#### Event Storming

- to create boundaries, structures 
- buttom up approach
- domain event
  - sg business relevant that happened
- command
  - tells the system what to do
- aggregate
  - conglomerate
  - need to be consistent according to some business rule
- read model
  - view of data for a specific use case
- policy
  - automated process
- event sourcing
  - CQRS (Command Query Responsibility Segregation)
  - technical solution
  - store events and restore actual state
  - one possibility to implement event storming 

### Domains

- problem space (=analysis): subdomains
  - core subdomain: use DDD (difficult tasks)
  - supporting subdomain (simpler solutions, probably jsut CRUD)
  - generic subdomain: e.g. accounting, just buy
- solution space
  - design & implementation
  - bounded context: ~ IT-teams
- decompose
  - collaboration with the experts
  - via requirements

#### Subdomains

- business domain
- not everything must be perfectly designed
- categories
  - core subdomain
    - invest money here
    - product not project
    - iteration
    - will change over time
    - do DDD here
  - supporting subdomain
    - may have complexity
  - generic subdomain
    - can be bought
- subdomains are not
  - the organizational structure of the company
  - technology
    - data storage
    - REST
    - sftp

### Domain Model

- use case driven
- temporarily valid
- analysis model
  - domain, only in theory
- code model
  - is The Model
  - Model Driven Development

#### Ubiquitous Language

- common language between stakeholders & developers (e.g product - with special meaning)
- must be the same in analysis and code
- PO shouldn't communicate with SQL queries
- do
  - consistent
  - keep a glossary
  - kiss
- don't
  - synonims
  - tech terms
- tools
  - gibberish naming
    - it a concept is unclear, give a "crazy name" until it becomes clear
  - class responsibility collaboration cards
  - keep a glossary

#### Layers

- interface: for users
- application layer: apply
- domain layer: domain logic

#### Documentation

- visualisation, easy to change (e.g. whiteboard)
- pragmatic

#### Challenges

- growing complexity
- multiple teams/experts/goals
- ambiguity in the language (e.g. ticket)
- amiguity of a concept (e.g. product)

### Bounded Context

- own ubiquitus language & model
- e.g product in all its contexts (marketing, sales, procurement, pricing)
- microservices
- subdomain (business context) ~ bounded context (solution context)
- teams are usually responsible for one context
- context game
  - pck a loaded word
  - go into separate rooms
  - after 15 min discussion see if results are the same

### Application Architecture

- onion model
  - domain layer (api) 
  - application service (use case services with interfaces) 
  - dependencies (with injection)

### Context Map

- reflects reality
- shows techninal realities of integration points between contexts
- shows organizational realities of integration points between contexts

#### Patterns

##### Shared Kernel

- kiss
- ~ common library

##### Anticorruption Layer

- UL translation
- only for translation, no logic here

##### Open Host Service

- use a public api

##### Directionality Strategies

- customer-supplier
  - teams agree on a contract (API)
  - customer joins the supplier's planning
- conformist
  - downstream context must conform to upstream's API
  - downstream needs may not be met at all

#### Integration Stretegies

##### Database Integration

- easy
- model is decoupled from BC
- contexts are coupled
- can cause problems (e.g. logging)
- changes in data model -> influence on all teams

##### RPC 

- remote procedure call
- hides the complexity of the network
- blocking I/O
- tight coupling on implementatiion
  - interface java vs REST

##### REST + Hypermedia

- descriptive API
- integrates with browser
- coupling only via explicit contract 
- stateless
  - client provides all the necessary application state
  - request can be load balanced
- still synchronous communication

##### Asynchronous Messaging

- loose coupling
- non-blocking
- resilient against downtimes
- events are descriptive
- but steep learning curve
- usually not platform independent

##### Consistency Consideration

- transactional vs eventual
  - roll-forward instead of roll-back
- transactional consistency
  - within a context
- eventual consistency
  - between contexts

### Tactical Patterns

#### Value objects

- immutable
- technical lifecycle (e.g. MonetaryAmount) 
  - can be an Entity in anouther domain
- does not require helper methods
- combineable (e.g. addition)
- self validation

#### Entity

- domain model 
- business lifecycle
- ID (e.g. Invoice)
- more complex logic
- delegated behaviour
- manipulate by explicit methods (not getter/setter)
- self validation
- with same names in different contexts might not have 1:1 relations

#### Domain Service

- to manipulate entities
- represent behaviour
- stateless

#### Domain events

- historical records
- immutable
- public properties
- used both in problem space and solution space
- internal events: part of Domain Model
- external events: between BCs
- commands
  - ~ events
  - imperative
  - have only one recipient

#### Aggregate

- tree of domain objects (entity & value objects) with ID reference
- all interactions via root entity
- transactional boundary
- prefer ID reference over object reference
- keep small

#### Repository

- domain model
  - free of technical dependencies
- application service
  - map use cases
- infrastructure
  - DB, ORM...
  - injected to domain model
- dependency inversion pattern
- one aggregate ~ one repository
- patterns
  - Unit of Work
  - Version Numbers

## REST-API Design

- REpresentational State Transfer
- Restful: REST implementation

### Maturity levels (level 1-3)

#### Level 1: Resouces

- resource ~ object
- communicaton with repesentations
- can be identified with an URIs (URL + URN)
- best practice: plural

#### Level 2: HTTP Verbs

- POST, GET, PUT (overwrite), PATCH (only parts), DDELETE
- Statuscodes
  - 2xx: OK 
    - 201 (created)
    - 204 (no content)
  - 3xx: forward
  - 4xx: Client error 
    - 401 (not authorized = not authenticated)
    - 403 (forbidden)
    - 404 (not found)
  - 5xx: server error / 500 (server error)
- HTTP header
  - content-type: of payload
  - accept: what the client accepts
  - MIME-types: can be customized (vnd.aaa.bbb.v1+json)

#### Level 3: links (HATEOS)

- HAL: a standard
- to header
- json hyperschema
- access control, flow, changable API
- OPTIONS request: which calls are available
- con: loads of requests

### Versioning

- MIME type
- path: v1/
- header
- through links (HATEOS)

### Documentation

- [RAML](https://raml.org/) RESTful API Modeling Language, YAML-based, for describing RESTful APIs
- [Open API](https://www.openapis.org/)

## Concepts

- AOP (Aspect-oriented Programming)
  - adding additional behaviour to existing code (without modifying the code)
  - ~ annotations
