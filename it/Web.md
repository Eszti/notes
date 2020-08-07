# Web

## API

- [quicktype](https://quicktype.io/): type generation
- [mock REST APIs](https://mockapi.io/)

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

## JavaScript

- conforms to ECMAScript specification
- WWW = HTML + CSS + JavaScript
- JavaScript engine
  - executes js code
  - early days: interpreters
  - modern: just-in-time compilation

### JS Runtime Environments (Frameworks)

- [node.js](https://github.com/nodejs/node)
  - open source
  - cross platform
  - executes JS code outside of a browser (server-side scripting)
  - version manager: [nvm - Node Version Manager](https://github.com/nvm-sh/nvm)

### JS package managers

- [npm- Node Package Manager](https://www.npmjs.com/)
  - default for Node.js
  - cli: for interaction from terminal
  - registry: large public database
  - website for browing packages

- [yarn](https://classic.yarnpkg.com/lang/en/)
  - released by fb
  - compatible with the public npm registry (and use it by default)
  - share code as package (~module) = code + package.json
  - package.json: ~metadata to the project
  - ~ alias for `npm run`

### JS compilers

- [Babel](https://github.com/babel/babel)
  - ~transcompiler
  - converts ECMAScript 2015+ into a backwards compatible version of JavaScript
  - used by React

### JS Module Bundler

- [webpack](https://github.com/webpack/webpack)
  - bundles js files for browser usage (for SPAs)
  - dev-server for on-the-fly update

### JS Applications

- SPA: single page application
  - server only for delivering packed code
  - runs in browser
  - use API requests for data acquisition
- MPA: multi-page application
  - each interaction sends a server request
  - historically for browsers that cannot run js
  - always delivers HTML

- [React](https://github.com/facebook/react)
  - syntax: jsx files: ~HTML + js code in {}
    - Babel for complie
  - React Components
    - render() method for rendering
    - Props: ~ HTML attributes
  - PureComponent: only renders that changed
  - Redux: store

- [Angular](https://github.com/angular/angular)
  - syntax: html + ts
  - components
    - html: ~render() in react
    - ts (TypeScript) files: code
      - @Component():  ~React.Component
      - @Input(): ~Props in react
    - css files
  - own template language (ng...)
  - compiler: in browser
  - only render what changed

### JS libraries

- [jQuery](https://github.com/jquery/jquery)
  - open source
  - simplifies
    - HTML DOM traversal & manipulation
    - event handling
    - CSS animation
    - Ajax
  - everything is in jQuery aka $ namespace

- [Redux](https://github.com/reduxjs/redux)
  - state container
  - most often with React

## Java web

- Java servlets: software component that extends the capabilities of a server
- web container (=serverlet container): component of a web server that interacts with servlets
  - managing lifecycle
  - mapping URL
  - ensure access rights

### JSP

- JavaServer Pages to create dynamically generated web pages, ~ PHP,ASP, but uses java
- document types: HTML,  XML, SOAP
- to deploy & run: web server with servlet container (Apache Tomcat, Jetty...)
- used as MVC
  - view: JSP
  - model: java beans
  - controller: java servlets

### Wicket

- component-based web application framwork
- not MVC, but stateful GUI like Swing

### [Jersey](https://github.com/eclipse-ee4j/jersey)

- REST framework
- provides JAX-RS reference implementation (own extended API)

## Frontend testing

- headless browser: browser without GUI, good for testing, renders like real browsers
- [cypress](https://www.cypress.io/)
  - end-to-end browser testing framework
  - can also headless
- [jest](https://jestjs.io/)
  - javascript test framework
  - mostly for unit & integration
- [Cucumber](https://cucumber.io/)
  - write human readable tests
  - mostly for e2e

## Userscripts

- Chrome: [Tempermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=de)
- Firefox: [Greasemonkey](https://addons.mozilla.org/de/firefox/addon/greasemonkey/)

## Concepts

- proxy
  - intermediary between client and server, potentially masking the true orgin of the request
  - types
    - open proxy (forwarding proxy
      - forwards requests
      - on behalf of the clients
    - reverse proxy
      - resources returned to the client appear as if they originated from the proxy
      - on behalf of the servers
