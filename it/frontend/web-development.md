# Web Development

## Architecture

### SPA

- single page application
- server only for delivering packed code
- runs in browser
- use API requests for data acquisition

### MPA

- multi-page application
- each interaction sends a server request
- historically for browsers that cannot run js
- always delivers HTML

### DOM

- HTML -> Parsing -> DOM object -> rendering
- (not necessarily) js: manipulates the DOM & re-render

## Browser

### Google Chrome

- hotkeys
  - [Ctrl+w]: close tab
  - [Ctrl+l/F6]: select URL

### Userscripts

- Chrome: [Tempermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=de)
- Firefox: [Greasemonkey](https://addons.mozilla.org/de/firefox/addon/greasemonkey/)

### Storeage

#### Cookies

- oldest
- most restrictive
- store data that has to be sent back to the server
- primarily for server-side reading
- can also be read on client-side
- expiration duration can be set both on server and client side
- can be made secure
  - httpOnly: prevents client-side access

#### Local storage

- key-value store on the client's computer
- no expiration date
- data is never transferred to the server
- plaintext

#### Session storage

- same as localstorage, but store only for the session (until browser is closed)

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

### Thymeleaf

- [Thymeleaf](https://www.thymeleaf.org/)
- server-side, java template engine 