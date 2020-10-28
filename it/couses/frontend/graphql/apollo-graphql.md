# GraphQL with Apollo

- [GraphQL docs](https://www.apollographql.com/docs/)

## Discover Apollo

- Apollo Server
  - you can define
    - GraphQL schema
    - resolvers
  - can deploy to any hosted/serverless environment
  - incremental adoption
  - federated architecture (multiple services merged by a gateway)

- Apollo Client
  - for querying the graph
  - caching (~query itself)
  - state management
  - define queries within the UI

- Apollo Studio
  - schema explorer
  - metrics reporting
  - cloud platform
  - schema registry tracks changes

- Apollo Federation
  - monolithic sever vs implementing services + gateway (all are GraphQL servers)

## Apollo Fetch Policies

- Apollo Client has a cache
- cache policies
  - cache-first
    - default
    - if all data is present in cache: no update
  - cache-and-network
    - returns from the cache
    - but updates the cache
  - network-only
    - always return from network
    - and update cache
  - no-cache
    - always return from the network
    - does not use cache at all
  - cache-only
    - never use network
    - e.g. for offline usage
- fetch policies can be set
  - entire applicatin
  - for queries
