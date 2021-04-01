# Distributed Systems

## API

- [quicktype](https://quicktype.io/): type generation
- [mock REST APIs](https://mockapi.io/)

## History

### Dawn of Distributed Computing

- 1970-80
- RPC
- messaging
- queuing

### Object Oriented APIs

- 1980-2000
- COM/DCOM (Microsoft)
- CORBA (Java community)
- Java RMI

### Web-Based APIs

- 2000-until now
- XMLHTTP
- REST (~2005)
- SOAP (Microsoft)
- GraphQL (facebook)
- gRPC (Google)

## RPC

- ~1970s
- remote procedure call
- call a subrutine in a different address space (on another computer), as if it were a local procedure

### RMI

- Java Remote Method Invocation
- Java API, performs RPC
- direct transfer of serialized java objects

## REST

### Concepts

- separation of client and server
- server requests are stateless
- cacheable requests
- uniform interface
  - HTTP methods
  - requests are made to a resource's URI
  - response can confirm alternation & can provide hypertext
- RESTful
  - web services with REST architecture, everything is a resource

### Problems

- too diffficult to be qualified as "REST"
- dogma of REST vs Pragmatism
- overfetching and underfetching
- server provides ALL the possible follow-up links that depend on resource state

### HATEOAS

- Hypermedia as the Engine of Application State
- REST application architecture
- server provides information dynamically through hypermedia
- REST client needs no prior knowledge about the API, only needs generic understanding of hypermedia
- how it works
  - client enters through a fixed URL
  - future actions are discovered

### REST vs GraphQL

- server-driven (REST) vs client-driven (GraphQL)
- join requests (REST) vs retrieve data in a single request (GraphQL)

## GraphQL

- query language
- [TypeGraphQL](https://typegraphql.com/)
  - GraphQL framework in node.js
  - schema in TypeScript
- needs a server (runs e.g. as a lambda) and a client (runs in browser) implementation

### Frameworks

- [Apollo](https://www.apollographql.com/)
  - server & client
  - automatic cache within one query (e.g. root is queried only once)
  - graphQL pulls continuously with a POST request, so that the schema is up-to-date
  - life cycle is only one query, no need for cache invalidate
- [urql](https://formidable.com/open-source/urql/)
  - client
- [GraphQL Helix](https://github.com/contrawork/graphql-helix)
  - server
- [GraphQL Nexus](https://nexusjs.org/)
  - for GraphQL schema construction
  - code-first (instead of schema-first) approach
- [GraphQL Typed Document Node](https://github.com/dotansimha/graphql-typed-document-node)
  - for typed document nodes
- [Prisma](https://www.prisma.io/)
  - client
  - query builder
  - works with Nexus

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
- [GraphiQL](https://github.com/graphql/graphiql)
  - GraphQL IDE

## Big Data

- [Gremlin](http://tinkerpop.apache.org/gremlin.html)
  - graph traversal language