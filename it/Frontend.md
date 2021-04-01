# Frontend

## JavaScript

- conforms to ECMAScript specification
- WWW = HTML + CSS + JavaScript
- JavaScript engine
  - executes js code
  - early days: interpreters
  - modern: just-in-time compilation
- basic
  - dynamic typing
  - prototype-based
  - object-oriented
  - first-class functions
  - multi-paradign (event-driven, functional, imerative)

### Runtime Environments (Frameworks)

- [node.js](https://github.com/nodejs/node)
  - open source
  - cross platform
  - executes JS code outside of a browser (server-side scripting)
  - version manager: [nvm - Node Version Manager](https://github.com/nvm-sh/nvm)
  - web application frameworks
    - [express](http://expressjs.com/): simple, well documented, but too heavy & slow

### package managers

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
  - `yarn cache clean`

- [bower](https://bower.io/)
  - only for front-end (html, css, js) packages

### compilers

- [Babel](https://github.com/babel/babel)
  - ~transcompiler
  - converts ECMAScript 2015+ into a backwards compatible version of JavaScript
  - used by React

### Module Bundler

- [webpack](https://github.com/webpack/webpack)
  - bundles js files for browser usage (for SPAs)
  - dev-server for on-the-fly update (also possible with nodemon)

### Frameworks

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

### libraries

- [React](https://github.com/facebook/react)
	- components
	- unidirectional data flow
	- virtual DOM
	- jsx files: ~ HTML + js code in {}
			- Babel for complie

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

- [Formik](https://formik.org/)
  - form validation
  - form handling & submission

### Tools

- [can I use](https://caniuse.com/)

## Angular

### Summary

- old Angular: AngularJS (= Angular 1)
- backed by Google
- TypeScript-based
- component-based

### Architecture

- NgModule
  - capsulate modules
- Directive
  - have an effect in rendered view
- View
  - rendered
- Component
  - View + Directive
- Pipe
  - filter & process values
- Service
  - functional code, e.g.call service

### Angular CLI

```bash
ng new my-app
cd my-app
ng serve
ng generate component XY
ng generate service XY
```

### Components

- selector: to reference
- template: html template
- style

```javascript
@Component({
  selector: 'app-root',
  templateUrl: './app.component.html',
  styleUrls: ['./app.component.less']
})
```

- interpolation
  - `{{ message }}`
- change detection
- dependency injection
  - constructor injection

#### Lifecycle

- ngOnInit
  - before first rendering
  - `implements OnInit`
- ngOnDestroy
- ngOnChanges

#### Data Binding

- `[item]`
- @Input()

#### Event Binding

- `(click)`
- @Output()

#### Directives

- `*ngIf`
- `*ngFor`
- `[(ngModel)]`: two-way data binding

#### Pipes

- to convert values
- `ng generate pipe`

#### Content Projection

- e.g to define a header
- `<ng-content />`

### Routing

- path-component associations in app-module
- redirect
- wildcard
- params: `books:/:bookName`
- nested routes
- navigate programatically
  - `router.navigate()`

### Testing

#### Unit

- [Karma](https://karma-runner.github.io/latest/index.html)

#### E2E

- [Protactor](http://www.protractortest.org/#/)

## React 

- [best practices](https://alexkondov.com/tao-of-react/)
  - favor Functional Components
  - name components
  - don't hardcode markup
  - destructure props
  - pass objects instead of primitives
  - use conditional rendering (&&)
  - move lists into a separate component
  - assign default props
  - use reducers
  - prefer Hooks (useForm vs Form)
  - group app structure by route/module
  - wrap external components (don't import them directly, a.k.a. use `import {}`)
  - don't rely on snapshot tests
  - use a data fetching library ([React Query](https://react-query.tanstack.com/) or [SWR](https://swr.vercel.app/))

### Getting started

- `npm init react-app my-app`
- files
	- App.js
		- React App Component
	- App.test.js
		- unit tests
	- App.css
		- style

### Components

- like classes
- two ways
	- class component
	- functional component (preferred)
- properties
	- read-only
	- injected from outside
- default properties
	- syles, className, onclick, children
- always one top level element, use empty tag: <>
- ...prop: to transfer all members
- js code: {}
- HOC (Higher-Order Components)
  - take and return a component

### States

- state
	- arbitrary objects
	- never change manually
- Class Component
	- initial state: ctor
	- update with setState
- Functional Component
	- use hooks: useState
	- hooks have to reside at the top level of a component
	- `const [count, setCount] = useState(0)`
	- use arrow functions to cope with quick updates

### Rendering

- on
	- mounting the component
	- changes to props
- virtual DOM
	- simplified DOM
- rendering process
	- compute new virtual DOM
	- compare current with the new
	- update only the differences
- component lifecycle (Class Component)
	- mounting: componentDidMount
	- updating: componentDidUpdate
	- unmounting: componentWillUnmount
- hooks lifecycle
	- same phases
	- useEffect
    - to implement side-effects in a FC
    - can observe objects

### React Context

- for global information
- e.g. language/i18n

### Styling

- create style object
- use the style property
- [styled-components](https://styled-components.com/docs)
  - tagged template literals for styling (string literals allowing embedded expressions)
  ```javascript
  const Title = styled.h1`
    font-size: 1.5em;
    text-align: center;
    color: palevioletred;
  `;
  ```

### Testing

- [RTL - React Testing Library](https://testing-library.com/docs/react-testing-library/intro/)
	- good testing practices
	- hook support
	- works with jest
	- data-testId: for not visible components
	- [cheatsheet](https://testing-library.com/docs/react-testing-library/cheatsheet/)
	- useful
		- first call render(<App />)
		- screen.queryAllByText()
		- userEvent.click()
- [enzyme](https://enzymejs.github.io/enzyme/)
- [react hooks testing library](https://react-hooks-testing-library.com/reference/api)

### Redux

- one store for whole application
- ~ context
- unidirectional data flow
- store
  - plain object
  - readonly
- update via actions
  - actions contains what happens
  - type & payload
- reducers defines how to update
  - simple function(state, action) => newState
  - no side-effects
  - can be split up
- useful
  - createStore
- debug
  - redux-devtools
- react-redux package
  - Provider
  - all components inside have access
  - useSelector
  - useDispatch

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

## Development

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

## Styling

### css

- span: vertical
- div: horizontal
- creating rows of fix length
```css
display: flex;
flex-direction: row;
flex-wrap: wrap
width: 600px;
```
- margin: outside
- border
- padding: inside
- learning links
	- [flexbox froggy](https://flexboxfroggy.com/)

### Less

- Learner Style Sheets
- backward compatible language extension for csv
- [less.js](http://lesscss.org/#overview)
  - converts Less style to CSS styles

## Testing

- headless browser: browser without GUI, good for testing, renders like real browsers

### Cypress

- end-to-end browser testing framework
- [Puppeteer](https://github.com/puppeteer/puppeteer)
  - headless library
- follows the `conditional testing` principle `If X, then Y, else Z`
- [cypress testing library](https://testing-library.com/docs/cypress-testing-library/intro/)
  - allows dom-testing queries
  - aria-labels can be used
    - provides the user with recognisable names of the object

#### Commands

```java
// Add new command
Cypress.Commands.add("clickCancel", (pattern) => {
  testCancelFlow(pattern);
});

// Call
cy.clickCancel(PAGES.OVERVIEW.title);
```

### Jest

- [jest](https://jestjs.io/)
- javascript test framework
- mostly for unit & integration
- runs a low level, plain JavaScript
- transformers
  - [esbuild-jest](https://github.com/aelbore/esbuild-jest)
    - fast
    - ts, js, tsx, jsx
- mocking
- exceptions
- snapshot tests
- setting: `jest.config.js`
- set up moduleDirectories for using relative paths
  - `moduleDirectories: ["node_modules", path.join(__dirname, "src")]`

### Cucumber

- [Cucumber](https://cucumber.io/)
- write human readable tests
- mostly for e2e

## UI Design

- [Storybook](https://storybook.js.org/)
  - to design and showcase components
  - React, Angular, Vue
  - story: captures a rendered state
  - can show code examples
- screenshot testing
  - [Storyshots](https://www.npmjs.com/package/@storybook/addon-storyshots)
    - ~ jest tests
    - snapshot testing for components
  - [Creevey](https://github.com/wKich/creevey)

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
