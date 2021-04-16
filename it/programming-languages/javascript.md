# JavaScript

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

## Runtime Environments (Frameworks)

- [node.js](https://github.com/nodejs/node)
  - open source
  - cross platform
  - executes JS code outside of a browser (server-side scripting)
  - version manager: [nvm - Node Version Manager](https://github.com/nvm-sh/nvm)
  - web application frameworks
    - [express](http://expressjs.com/): simple, well documented, but too heavy & slow

## package managers

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

## Compilers

- [Babel](https://github.com/babel/babel)
  - ~transcompiler
  - converts ECMAScript 2015+ into a backwards compatible version of JavaScript
  - used by React

## Module Bundler

- [webpack](https://github.com/webpack/webpack)
  - bundles js files for browser usage (for SPAs)
  - dev-server for on-the-fly update (also possible with nodemon)

## Frameworks

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

## Libraries

- [jQuery](https://github.com/jquery/jquery)
  - open source
  - simplifies
    - HTML DOM traversal & manipulation
    - event handling
    - CSS animation
    - Ajax
  - everything is in jQuery aka $ namespace
- [React](https://github.com/facebook/react)
	- components
	- unidirectional data flow
	- virtual DOM
	- jsx files: ~ HTML + js code in {}
			- Babel for complie
- [Preact](https://preactjs.com/)
  - small react
- [Redux](https://github.com/reduxjs/redux)
  - state container
  - most often with React
- [Formik](https://formik.org/)
  - form validation
  - form handling & submission
- [Blitz.js](https://blitzjs.com/)
  - fullstack react framwork

## Build Tools

- [Vite](https://vitejs.dev/guide/)

## Tools

- [can I use](https://caniuse.com/)
