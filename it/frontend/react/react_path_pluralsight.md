# React

## All the JS before starting with React

- [summary](https://jscomplete.com/learn/javascript-for-react)

## Big Picture

### Why

Flexibility

- learn one, write everywhere
- different renderers
  - server-side rendering

Developers' experience

- jsx -> javascript
- traditional:
  - Angular, vue, ember: enhance html with custom keywords / fake js in html
  - React: handle html with javascript / fake html in javascript
- detailed error messages
- create-react-app
- CodeSandbox

Corporate Investment

- facebook developers (fb, insta, whatsapp)
- react-codemod (automate updates)

Community

- popular
- fabric (MS), material (Google), bootsrap
- ecosystem: complex data flows (redux, mobx), Restful (GraphQL), testing (jest)

Performance

- dom optimization
- React ~35k, Inferno: ~9k, Preact: ~3k (same API, easy to change)

Testability

- unit tests are possible
- javastring test libraries: jest (fb)
- no side-effect functions

### Tradeoffs

Framework vs Library

- framework: angular & ember
  - clear opinions, less setup, more consistency
- library: React
  - ligth-weight, sprikle on existing apps (also server-side php appls), pick only what you need
  - popular boilerplate, almost framework
  - features: waht you want

Consise vs Explicit

- two-way binding: angular
- one-way bindig: react
  - declare precisely, easy to debug

Template-centric vs JS

- "js" in HTML: angular
  - no js knowledge is needed, avoid confusion
- "html" in js: react
  - autocomplete,  little framework-specific syntax, need to learn modern js

Separate template vs Singe File

- MVC
- each component stands on its own (separation of concerns)
  - trad: diferent technologies to diff files
  - react: each component is a separate files
  - compose

Standard vs Non-standard

- non-standard, like everything in web
- why not? -> browser renders
- web components:
  - template
  - custom elements
  - shadow dom (style)
  - imports

  Community vs Corporate backing

  - facebook: driven by fb's needs
  - full-time development staff
  - 1000+ contributors

### Why not

JSX vs HTML

- only 99% similar
- jsx is compiled to js (for, class, style, comment)
- existing html: find, online, npm: htmltojsx

Build Step Required

- build js is also needed
- Transpilers: Babel, TypeScript (source-to-source compiler)

Version Conflicts

- runtime: consistent versions
- you need to keep it up-do-date anyway
- upgrade when you upgrade libraries

Old Stuff Online

- community
- check doku (maintained by fb)

Decision Fatigue

- too many options
- dev env
  - boilerplate projects
    - official: create-react-app
    - realated libs not in
- ES Class vs createClass
  - ES Ckass: without extra lib
- types
  - propTypes (only at runtime, at dev), TypeScript (MS, superset of js, ~C#/Java, compiles to js, checks types at compile time), Flow (fb creation, checks when you run flow)
  - propTypes for beginners
- state management = store data
  - plain react (for starting)
  - flux (fb)
  - Redux (most popular)
  - MobX (observable data structures, less code)
- Styling
  - plain css
  - recommended: what you already know

## Getting started

### The Basics

- 16.8 Hooks

#### Why React

- javascript library
- for building user interfaces
- small: do one thing and do it right
- you need to use other libraries
- declarative
  - describe final state
  - react takes care for updating
- framework
  - design decisions are already made
  - not flexible
  - large
  - hard to customize
- virtual DOM
- React Native for mobile apps
- battle-tested

#### React's Basic Concepts

- Components
  - simple js functions
  - input
  - reusable
  - html
  - private state
  - two types
    - Function Component (preferred)
      - proops
    - Class Component (more powerful)
      - state
- Reactive updates
  - auto update to the browser
- Virtual views in memory
  - no html templates
  - generates html using js

- First Component
  - jsx
    - executed by jsx extension
    - uses Babel (try out)
    - React.createElement or `<Hello>`
  - always name with Upper case
