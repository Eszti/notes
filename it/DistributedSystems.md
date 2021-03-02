# Distributed Systems

## API

- [quicktype](https://quicktype.io/): type generation
- [mock REST APIs](https://mockapi.io/)

## RPC

- remote procedure call
- call a subrutine in a different address space (on another computer), as if it were a local procedure

### RMI

- Java Remote Method Invocation
- Java API, performs RPC
- direct transfer of serialized java objects

## REST

- server-driven
- allow to access & manipulate web resources by using stateless operations
- requests are made to a resource's URI
- response can confirm alternation & can provide hypertext
- HTTP methods can be used
- RESTful: web services with REST architecture: everything is a resource
- problems
  - overfetching and underfetching
  - server provides all the possible follow-up links that depend on resource state

### HATEOAS

- Hypermedia as the Engine of Application State
- REST application architecture
- server provides information dynamically through hypermedia
- REST client needs no prior knowledge about the API, only needs generic understanding of hypermedia
- how it works
  - client enters through a fixed URL
  - future actions are discovered

## GraphQL

- query language
- client-driven
- advantages to rest
  - retrieve data in a single request (REST: multiple request, ~ join tables)
- [TypeGraphQL](https://typegraphql.com/)
  - GraphQL framework in node.js
  - schema in TypeScript

- server: lambda (apollo-server)
- client: runs in browser (apollo-client)
- life cycle is only one query, no need for cache invalidate
- automatic cache within one query (e.g. root is queried only once)
- graphQL pulls continuously with a POST request, so that the schema is up-to-date

### Development steps

- schema
  - defines the query fields
- resolver
  - resovles gql query fields
- data source
  - gets the data (e.g. REST API calls)
- .gql files (queries, mutations...)
  - define queries & mutation for GUI
- React frontend
  - use apollo-client implementation for calling GraphQL scripts

### Tools

- [GraphQL Voyager](https://github.com/APIs-guru/graphql-voyager)
  - represent GraphQL API as an interactive graph
