# Notes

## Architecture

### API to services

* [blog](https://nordicapis.com/building-a-backend-for-frontend-shim-for-your-microservices/)
* Classical Approach
  * one general API
* Microservice Design
  * each application client type has its own dedicated API
  * lots of duplications
* Backend for Frontend (BFF)
  * use shims for translation services

### Approaches

#### BDD: Behaviour Driven Development

* [Cucumber](https://cucumber.io/)
  * Gherkin: language parser
  * describe software behaviour with logical language
  * enables automatic acceptance tests

#### DDD: Domain Driven Development

* situation: scrum team (implementation) ---- stakeholders + domain experte (context & details)
* official book: 2004
* Domains
  * problem space (=analysis): subdomains
    * core subdomain: use DDD (difficult tasks)
    * supporting subdomain (simpler solutions, probably jsut CRUD)
    * generic subdomain: e.g. accounting, just buy
  * solution space (=design & implementation): bounded context, ~IT-teams
* Model
  * Analysis model: domain, only in theory
  * code model: is The Model  -> Model Driven Development
  * ubiquitous language: common language between stakeholders & developers (e.g product - with special meaning)
  * knowledge crunching: **evnet sourcing** domain events
    * ~ domain model, start with a kick-off workshop, than iterate, use these event for communication
* Bounded context
  * own ubi.lang. & model
  * decompose it to **business components** and **components**
  * ~ microservices
* application architecture
  * onion model: domain layer (~api) -> application service (use case services with interfaces) -> dependencies (with injection)
* context map: relationship between BCs
  * e.g. how to translate ubi.lang.
  * patterns: shared kernel, conformist, anticorruption, open host service...
  * connenting BC: RPC, REST, FTP, Commands & Events, Message Broker (sync or async)
  * **eventual consistency** instead of *transactional consistency* (roll-forward instead of roll-back)
* tactical patterns
  * Value objects: immutable, technical lifecycle (e.g. MonetaryAmount) -> can be an Entity in anouther domain
  * Entity: domain model lifecycle, ID (e.g. Invoice)
  * Domain Service: behaviour, stateless
  * Domain events: historical records, immutable
  * Aggregate: tree of domain objects (entity & value objects) with ID reference

## Web

### REST

* server-driven
* allow to access & manipulate web resources by using stateless operations
* requests are made to a resource's URI
* response can confirm alternation & can provide hypertext
* HTTP methods can be used
* RESTful: web services with REST architecture: everything is a resource
* problems
  * overfetching and underfetching
  * server provides all the possible follow-up links that depend on resource state

#### HATEOS

* Hypermedia as the Engine of Application State
* REST application architecture
* server provides information dynamically through hypermedia
* REST client needs no prior knowledge about the API, only needs generic understanding of hypermedia
* how it works
  * client enters through a fixed URL
  * future actions are discovered

### GraphQL

* query language
* client-driven
* advantages to rest
  * retrieve data in a single request (REST: multiple request, ~ join tables)
* [TypeGraphQL](https://typegraphql.com/)
  * GraphQL framework in node.js
  * schema in TypeScript

### Java web

* Java servlets: software component that extends the capabilities of a server
* web container (=serverlet container): component of a web server that interacts with servlets
  * managing lifecycle
  * mapping URL
  * ensure access rights

#### JSP

* JavaServer Pages to create dynamically generated web pages, ~ PHP,ASP, but uses java
* document types: HTML,  XML, SOAP
* to deploy & run: web server with servlet container (Apache Tomcat, Jetty...)
* used as MVC
  * view: JSP
  * model: java beans
  * controller: java servlets

#### Wicket

* component-based web application framwork
* not MVC, but stateful GUI like Swing

#### [Jersey](https://github.com/eclipse-ee4j/jersey)

* REST framework
* provides JAX-RS reference implementation (own extended API)

### Userscripts

* Chrome: [Tempermonkey](https://chrome.google.com/webstore/detail/tampermonkey/dhdgffkkebhmkfjojejmpbldmpobfkfo?hl=de)
* Firefox: [Greasemonkey](https://addons.mozilla.org/de/firefox/addon/greasemonkey/)

### Tests

* headless browser: browser without GUI, good for testing, renders like real browsers
* cypress: end-to-end testing framework, can also headless

## DevOps

### docker-compose

* defining & running multi-containers

### AWS

* run local: [localstack](https://github.com/localstack/localstack)
* CodePipeline: CI
* SFTP as managed service

## Languages

### C++

#### C++20

* modules
  * no more #inluce
  * export & import
  * faster compiliation, no more .h/.cpp
* concepts
  * requires(): compiler feature with static_assert, constraints for templates
  * conceipts: complie time predicate, template definition (e.g. what behaves like a boolean)
* ranges
  * a conceopt
  * e.g. sort without .begin() & .end()
  * views: requirements of a range with O(1) copy/move/assignment operations
  * pipes: applicable for unary adopters
* coroutines
  * co_yield, co_return, co_await
  * 2 types: with & w/o stack
  * e.g. for generators, lazy evaluation, event driven programming
* lambdas (since C++11)
  * default initialisation, can be members

### Java

* [sdkman](https://sdkman.io/install): multiple sdk version (e.g. java)

#### Concepts

* POJO: plain old java object: ordinary java object
* JavaBean: classes, encapsulate many objects, servializable, no-arg ctor, have getter & setter, used as standard

#### Important libraries

* [Dataprovider](https://github.com/TNG/junit-dataprovider) by TNG

#### Code snippets

``` java
    // Test with exception:
    // when
    ThrowingCallable callable = () -> uut.doSomething(a, b);

    // then
    assertThatCode(callable)
        .isInstanceOf(ExpectedException.class)
        .hasMessage("Object " + id + " does not exist. Or whatever");
```

#### Validation

* [Hibernate Validator](https://docs.jboss.org/hibernate/validator/5.4/reference/en-US/html_single/#validator-gettingstarted-createmodel)

#### Maven

* `mercateo# mvn install -am -pl trex.agent.catalog.management -DskipTests`

### JavaScript

* [yarn](https://yarnpkg.com/):package manager built by fb, Google, Exponent & Tilde

#### Tesing

* [jest](https://jestjs.io/)

#### node.js

* JavaScript runtime environment, executes JavaScript outside of a browser
* [nvm - Node Version Manager](https://github.com/nvm-sh/nvm): multiple node.js versions with default
* [npm](https://www.npmjs.com/): node package manager, yarn alternative

### Python

* [wtfpython](https://github.com/satwikkansal/wtfpython)

## Tools

### IntelliJ

* Plugins/extra tools
  * update: [JenBeans Toolbox](https://www.jetbrains.com/toolbox-app/)
  * key promoter x plugin
* Important hotkeys
  * alt+shift+left_arrow: navigate back
  * alt+J: multiple cursor
  * ctrl+E: recent files
* Important features
  * zen & presentation mode
* Solved issues
  * broken markdown (javaFX error): choose another java runtime for the IDE (with plugin)

### Atlassian

* ? : open shortcuts
* g + g: quick search
* Jira: bulk change: search: tools -> bulk change: edit, change label...
* [Jira rest API](https://developer.atlassian.com/server/jira/platform/rest-apis/)

### git

* configs: local, global (all repos), system (all users)

```bash
git config credential.helper store // unencypted, protected only by file permissions
```

* delete remote branch:

```shell
git push <remote_name> :<branch_name>
```

* ignore locally: git update-index --skip-worktree _file_
* reverse: git update-index --no-skip-worktree _file_
* [git bash prompt](https://github.com/magicmonty/bash-git-prompt)
* [Monorepo](https://www.atlassian.com/git/tutorials/monorepos)

## Documentation & Guidelines

### Documentation

* `CONTRIBUTING.md`: how to contribute to the projekt, [GitHub examples](https://help.github.com/en/github/building-a-strong-community/setting-guidelines-for-repository-contributors#examples-of-contribution-guidelines)
* [semantic versioning](https://semver.org/spec/v2.0.0.html)
* [acsiidoc](https://asciidoc.org/)
  * human-readable markup document format, better syntax for tables, admonitions...
  * converter to different backends (e.g. html, pdf, epub...)

### Coding syle

* [prettier](https://prettier.io/): code formatter, supports mainly front-end languages

## Data Science

* Machine Learning Version Control System: [DVC](https://dvc.org/)

## Database

H2

* RDBMS written in java
* can be embedded in java applications in client-server mode
* open source
* IF: SQL, JDBC, PostgreSQL ODBC

JDBC

* API how a client access a database
* java based

ODBC

* Open Database Connectivity
* API for accessing a DBMS

MongoDB

* NoSQL
* general purpose, document-based, distributed database
* [indices](https://emptysqua.re/blog/optimizing-mongodb-compound-indexes/)

## OS

### Windows

* [WSL](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux): linux in Windows

Package Manager

* [winget](https://github.com/microsoft/winget-cli), [doku](https://docs.microsoft.com/en-us/windows/package-manager/)

### Linux

#### Useful

* list key-bindings: `gsettings list-recursively  org.gnome.desktop.wm.keybindings | sort | more`
* `Alt>Esc` : cycle-windows
* `Alt>0` : switch in application

#### Packages

* rpm: for Red Hat based (CentOS, Fedora)
* deb: for Debian based (Ubuntu) (sudo apt install /path/to/file)

#### Package Manager

* dpkg
  * Debian Package Manager, low level
  * database: /var/lib/dpkg (in status file are the installed packages)
* apt
  * Advanced Package Tool, higher-lever tool, can fetch from remote & resolve dependencies: tools like apt/apt-get... can interact with it
  * apt is a subset of apt-get & apt-cache, start using apt
  * softwares can be installed with apt
  * update: updates the list of available packages but does not installs/upgrades
  * upgrade: installs available updates
* Homebrew

#### Bash Commands

* debug: set -o xtrace
* free disk space: df -h

#### Softwares/Tools

* [autojump](https://github.com/wting/autojump): instead of aliases
* Terminator
* KeePassXC
* Shutter

#### Errors

Problem

```shell
E: Sub-process /usr/bin/dpkg returned an error code (1)
```

Solution

```shell
sudo rm /var/cache/debconf/*.dat
sudo dpkg --configure -a
```

Problem

* Bluetooth cannot be turned on

Solution

```shell
sudo apt-get install --reinstall bluez  // and reboot system
```

## Protocols

FTP

* client-server architecture (FTP Server)
* separate control and data connection between client and server
* clear text authentication / anonymous
* does not encrypt contect
* active & passive mode
* server:
  * port 21: FTP server command port
  * port 20: FTP server data port
* client: TCP control connection from random (unprivileged) port
  * active: sends PORT M to server where it listens, then server initiates
  * passive: send a PASV, server sends IP:port, client opens a connection from an arbitrary port
* vsftpd: FTP server for Unix-like systems

FTPS

* FTP over SSL
* support for TLS and SSL(prohibited)

SFTP

* not compatible with FTPS
* SSH FTP
* ~remote file system protocol (file access, file transfer, file management(mv, cp, rm...))
* SFTP server: usually provided by an SSH server implementation
* shares port 22 with SSH
* extension of SSH

SCP

* Secure Copy Protocol
* only allows file transfer
* based on SSH
* Since 2019 April: outdated
* modern protocols: sftp, rsync

TLS

* at least one of following
  * private connection (handshake, symmetric cryptography)
  * authentication by public-key-cryptography
  * reliable connection: checksum (message integrity)

RFC

* [Key words for use in RFCs to Indicate Requirement Levels](https://tools.ietf.org/rfc/rfc2119.txt)
