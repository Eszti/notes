# Web

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

- development steps
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

## Browser

### Google Chrome

- hotkeys
  - [Ctrl+w]: close tab
  - [Ctrl+l/F6]: select URL

### Userscripts

- Chrome: [Tempermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=de)
- Firefox: [Greasemonkey](https://addons.mozilla.org/de/firefox/addon/greasemonkey/)

## Security

### Proxy

- intermediary between client and server, potentially masking the true orgin of the request
- types
  - open proxy (forwarding proxy
    - forwards requests
    - on behalf of the clients
  - reverse proxy
    - resources returned to the client appear as if they originated from the proxy
    - on behalf of the servers

### CIA Triad

- confidentiality
  - information is not made available for unauthorized
  - hacker reads sensible information
  - two-factor auth...
- integrity
  - accuracy & completeness = maintain the consistency
  - hacker/software bug/human error changes information
  - authentication, hash checks, redundancy
- availability
  - being accessible & usable on demand
  - DoS (denial-of-service) attack
  - intrusion detection, firewalls

### Crypto

- encoding
  - not really cryptographgy
  - Base64
    - transform all kinds of bytes to a specific range (ASCII readable)
    - reversible
    - transform each 6 bit to a byte (8 bits) -> 33% increase
    - Basic Authentication uses Base64 encoding
  - HTML
    - space is not allowed in URL -> %20
- hashing
  - for detecting if the original data has been changed
  - if the orginal data changes - hash changes
  - irreversible
  - not recommended: MD5, SHA-1 (changed payload can still generate the same password)
  - salted hashes
    - pw + unique, randomly generated string -> hash
    - not possible to determine identical passwords
    - modern hashing algos have it by default (Argon2, Bcrypt)
    - store salt & pw hash
- encryption
  - symmetric
    - shared secret used both for encryption & decryption
    - AES, 3DES
  - asymmetric
    - key pairs (private & public)
    - private: secret
    - public: freely accessible
    - encrypted with private key, can only be decripted with the public key
    - decrypted wtih public key, can only be encrypted with the private key
    - RSA, DSA
  - HTTPS uses both
    - browser gets certificate, looks up if it can be trusted and gets the public key of the server
    - browser generates random symmetric key and encrypts it with the public key
    - only the server can decrypt the symmetric key with its private key
    - they communicate with the symmetric key

### Signing

- for checking the validity of the data
- when integrity is important
- A creates hash and encrypts it with private key
- B creates hash and decodes the encrypted data with public key, then compares
- data, signature, certificate

### Keystores

- keystore: for keys
- truststore: for trusted certificates and public keys (browser & OS)
- Let's Encrypt: creates trusted certificates

## Web exploits

- Pentest = Penetration test
  - ethical hacking

## Design

- [Storybook](https://github.com/storybookjs/storybook): UI components development in isolation
  - storyshots: snapshot testing for components
