# Learning GraphQL - Alex Banks; Eve Porcello

## Chapter 1. Welcome to GraphQL

- GraphQL
  - query language for your API & runtime for fulfilling queries
  - transport agnostic, typically over HTTP
  - declarative data-fetching language (what we need, instead how)
  - server can be written in ANY language
  - fb in 2012, released in 2015 (reference impl. graphql.js)

- GraphQL Spec
  - GQL is a spec for client-server communication
  - spec
    - describes language capabilities
    - common vocab & best practices
    - ~ ECMAScript
    - smart people get together and devise

- GQL design principles
  - hierarchical
  - product centric
  - strong typing
  - client-specified queries
  - introspective: able to query server's type system

- History of data transport
  - RPC: not yet client-server but similar
  - SOAP: XML & HTTP, resource oriented calls
  - REST: resource-oriented architecture
    - drawbacks
      - overfetching
      - underfetching
      - managing endpoints

- GQL clients
  - to speed the workflow of app developers
  - handle
    - network requests
    - data catching
    - injecting data into UI
- [Relay](https://relay.dev/): fb impl, for React
- [Apollo](https://www.apollographql.com/): framework agnostic

## Chapter 3. The GraphQL Query Language

- SQL - GQL
  - queries: DB - API
  - data stored: in DB - anywhere (DB, API, WebSocket)
  - SELECGT: Query
  - INSERT, UPDATE, DELETE: Mutation
  - listen for data changes: Subscription

- GraphQL API tools
  - [GraphiQL]
  - [GraphQL Playground]

- GQL requests
  - strings sent in the body of a POST request to a GraphQL endpoint
  - JSON response with data or error

- GraphQL root types
  - Query
    - selection sets: fields selected in curly brackets, can be nested
    - query arguments: for filter & selection
    - fragments: reusable selection sets on a specific type, spread operator (...Fragment)
    - inline fragments: on Type
    - query variables: starts with $ character
    - introspection
      - __schema query: to query details about the current API's schema
      - __type query: to see every available type
  - Mutation
    - if return an object, we'll need to use a selection set
  - Subscription
    - to get real time updates pushed by the server
    - works over a web socket
    - unsubscribe for stop listening

- GraphQL types
  - fields
    - scalar types: Int, Float, Boolean, String, ID
    - object types: defined in schema
  - union type: can return multiple types
  - interface: abstract type, list of fields to implement
  - definitions
    - OperationDefinition
      - contains only one of the 3 operatin types
      - OperationType + SelectionSet
    - FragmentDefinition

- AST (Abstract Syntax Tree)
  - query processing
    - lexical analysis: parsing keywords, arguments, brackets...
    - AST parsing: for easy modifications
  - GQL can traverse the AST & validate against GQL language & the current schema
