# Learning GraphQL - Alex Banks; Eve Porcello

## Chapter 1 - Welcome to GraphQL

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
