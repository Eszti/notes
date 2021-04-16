# GraphQL

- query language
- [TypeGraphQL](https://typegraphql.com/)
  - GraphQL framework in node.js
  - schema in TypeScript
- needs a server (runs e.g. as a lambda) and a client (runs in browser) implementation

## Frameworks

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

## Development steps

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

## Tools

- [GraphQL Voyager](https://github.com/APIs-guru/graphql-voyager)
  - represent GraphQL API as an interactive graph
- [GraphiQL](https://github.com/graphql/graphiql)
  - GraphQL IDE