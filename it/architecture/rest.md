# REST

- REpresentational State Transfer
- Restful: REST implementation

## Concepts

- separation of client and server
- server requests are stateless
- cacheable requests
- uniform interface
  - HTTP methods
  - requests are made to a resource's URI
  - response can confirm alternation & can provide hypertext
- RESTful
  - web services with REST architecture, everything is a resource

## Problems

- too diffficult to be qualified as "REST"
- dogma of REST vs Pragmatism
- overfetching and underfetching
- server provides ALL the possible follow-up links that depend on resource state

## HATEOAS

- Hypermedia as the Engine of Application State
- REST application architecture
- server provides information dynamically through hypermedia
- REST client needs no prior knowledge about the API, only needs generic understanding of hypermedia
- how it works
  - client enters through a fixed URL
  - future actions are discovered

## Maturity levels

### Level 1: Resouces

- resource ~ object
- communicaton with repesentations
- can be identified with an URIs (URL + URN)
- best practice: plural

### Level 2: HTTP Verbs

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

### Level 3: links (HATEOS)

- HAL: a standard
- to header
- json hyperschema
- access control, flow, changable API
- OPTIONS request: which calls are available
- con: loads of requests

## Versioning

- MIME type
- path: v1/
- header
- through links (HATEOS)

## Documentation

- [RAML](https://raml.org/) RESTful API Modeling Language, YAML-based, for describing RESTful APIs
- [Open API](https://www.openapis.org/)

## REST vs GraphQL

- server-driven (REST) vs client-driven (GraphQL)
- join requests (REST) vs retrieve data in a single request (GraphQL)

## Tools

- [mock REST APIs](https://mockapi.io/)