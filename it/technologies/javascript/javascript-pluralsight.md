# Javascript

## Big Picture (HTML, CSS & js)

internet vs web

- internet: network of networks, ~big book store, ~hardware, from the 80s
- web (www): collenction of information, ~books, ~software, from the 90s

HTML

- '93
- advanced elements
  - header, main, footer...
  - audtiosource, video, canvas, form
- HTML generating frameworks
  - ASP.NET MVC
  - php
  - java
  - ruby
  - python
  - node.js
  - go
  - wordpress: blogging engine
  - ghost.com

CSS

- '95
- cascading: priority: selector, .class, #param
- @media: responsive
- support: caniuse.com
- libraries: written by others
  - Bootstrap, ionic, materialize ...
- css preprocessor: variables can be used
  - less...

Javascript

- '95
- make html more interactive
- high level, interpreted
- looks like java, but implementation is different
- implementation of ECMAScript
- ajax calls: async, do not have to refresh the page
  - enables to call APIs
- libs & frameworks
  - JQuery, Bootstrap
  - angular, ember, node, vue, react, TypeScript

HTML & CSS & JS

- implemnted by web browsers

## Getting Started

### Intro

- programming language of the web
- web pages, business apps, utility apps, games
- Unity (game engine), TypeScript (superset)
- full-fledged (mac, win): electron
- server-side code: node.js
- needed software: git, npm

### JS Beginnings

- to change the html
- formatting
  - whitespace does not matterű
- error
  - we cannot see -> developer tool, console
  - console.log: any messages
- case sensitivity
- comments
  - // single line comment
  - /**/ multiline

### Variables & Constants

let total = 149.99;
let product = 'Hiking Boots'; // single&double quotes as well
let discounted = true;

Variable

- must start with a number
- _: private
- let price; // undefined

Constant

- not supposed to change
- const price = 40;

var vs let:

- old js: var
- var: we don't get errors

### Types and Operations

[mdn web docs](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

Numbers

- ++price vs price++
- operator precedence: maths
- precision: pay attention!
- 20 - -2; // use parenthesis

Strings

- single/double quotes
- backslash: escape
- backquotes: string interpolation

Convert

- toString: auto
- Number.parseFloat('123.12');
- NaN: not a number

null and undefined

- let saved: undefined
- saved = null;
- avoid: saved = undefined;

Objects & Simbols

let person = { name = "Schafboy" };

### Program Flow

Conditions

- === : identically equal, compares the same type
- !== : not identically equal
- ==: 1 == '1': true
- Ternary operator: ? : operator

Truthy & Falsy

- falsy: false, 0, "", '', null, undifivned, NaN
- truthy: !falsy

Block Scope

- let & const: has scope
- var: leaks

Loops

- for (let i=0; i < 5; i++)
- while, do..while

### Functions

fuction showMessage() {}

function expression: let fn = function // function decoration // () {} -> call: fn();

Parameters

- not passed values: undefined

Return

- default return value: undefined

Function Scope

- local variable
- functions have access to outer scope
- modify web page: document.getElementById

### Objects & DOM

Object Properties

- let person = { name: "John", age: 32, [secret]:  'secret' ...}
- person.name = person['name']

Object Methods

- { showInfo: function() { showMessage(this.name)} }

Passing Objects to a Function

- objects passed by reference

Built-in Objects

- Array, Date, String, Number...
- let date = new DAte();

Document Object Model (DOM)

- document
- styling: header.style.frontWeight = '800';
- detect button clicks: button.addEventListener('click', function() {} );
- show & hide
  - review.classList.remove('d-none');

### Arrays

Initialize

- let values = [ 1,2,3 ];
- Array.of()

Access Items

- values[0], out of bound: undefined

Manipulate

- push, pop, shift: takes the first, unshift: put as first
- slice: creates a new array from to
- splice: from where, how  many to delete, what to add

Searching & Looping

- values.filter(lambda), find, forEach

Arrays in the DOM

- HTMLCollection

### Scope & Hoisting

Global Scope

- global vs function
- global also refers to imports
- best prectice: one global object: app

Function Scope

- local variables & params
- function can have local functions

var & Hoisting

- var allows using a variable before it was declared
- Hoisting is ok for functions

Undeclared Variables & Strict Mode

- 'use strict': forces to use variables

## JS Fundamentals

### Intro & Setup

- Desktop: Electron
- Smartphone: Cordova
- server: NodeJS

History of js

- created: 1995
- ECMAScript

- webpack

### JS Language Features

rest parameters

- ...allCarIds: any paramter can be sent to a function -> rest of the parameters before optional, after: not allowed

Destructuring arrays

- assign array to variables
- let [a, b, b] = array
- can be combined with rest params
- ,: skip

Destructuring objects

- ~ assign object to structure fields
- use let or ()

Spread syntax

- break array/string into elements
- rest & spread can be used at the same time

Typeof()

- null: object
- undefined: undefined
- NaN: number
- fuction, object...

Conversions

- toString()
- Number.parseInt/Float...

Loops

- for(; i<3; i++)
- continue, break

### Operators

Equality

- ==: try to convert the variables to the same type ( 1 == true, 1 == '1')
- ===: identically equal (recommended)

Unary

- ++var: pre-increment
- var++: post-increment
- +var: convert string to number
- -var: negate value

Logical

- &&, ||: && has higher precedence!
- !
- console.log( userSettings || defaultSettings ): use user, if not present, then default

Relational

- <, >....
- strings: upper case comes before lower case

Conditional

- (exp) ? yes : no

Assignment

- +=, -= ... >>= (multiply/divide by 2)

Operator Precedence

- mult before add

### Functions & Scopes

Fuction Scope

- if a func does not find a variable it looks its parent and so on
- block scope: if, for...

IIFE pattern

- Immediately Invoked Function Expression
- (func)();
  - can be assigned

Closures

- hang function on objects
- this
  - context
  - to reach properties

Call & Apply & Bind

- change the context of this
- apply: with params
- bind: copy functions

Arrow Functions

- lambda: =>
- (): 2 or more params
- {}: we do need the return value
- _ instead of ()
- arrow functions do not have a this

Default Parameters

- ~python with =

### Objects & Arrays

- contructor
- this must be written out
- prototype (to not duplicate functions)
- JSON.stringify - JSON.parse
- ids.foreach( arrow function )
- ids.filter()
- ids.find()
- ids.every()

### Classes & Modules

- class (uppercase)
- constructor()
- function()
- iheritance: extends
- modules: organise classes
  - export
  - import from

### Programming the BOM & DOM

- Browser Object Model
- window
  - global object in JS
  - properties & methods
  - modules: window not the global object
- timer
  - setTimer, setInterval
- location
  - href, pathname...
  - also available from DOM

- Document Object Model
- getElementById, ...sByClassName, ...sByTagName
- can be modified: add, =...

### Promises & Error Handling

- error handling
  - try - catch - finally
- own errors
  - new Error
- Promise
  - async, temporary holder
  - resolve: handle success value
  - reject: handle error value
  - then: if resolves successfully

### Data Access Using HTTP

- XHR
  - Xml HTTP Request
  - readyState & status
  - manual
- jQuery
  - import $
  - returns promises
  - post

### Forms

- direct submission with submit type button
  - form.addEventListener + preventDefault
- submit -> validaton & format -> send to server
- event.preventDefault

### Security

- chrome developer tools (F12)
  - webpack budles source code
  - eval
  - do not use passwords & global variables
  - js obfuscator
- eval: to execute string code
- man-in-the-middle-attack
  - scripts insertion
  - use ssl
  - use HTTP header
- cross-site scripting attack (XSS)
  - script is needed from a 3rd party server
  - CSP: Content-Security-Policy (header)
  - CORS: Access-Control-Allow-Origin (header)
- production with webpack
  - npm run dev
  - npm run build
    - dist folder
    - can be distirbuted on a server
    - minimised

## JS Objects & Prototypes

### Creating JS Objects

- Plunker: online js editor
- 'use strict'
- no classical classes
- create objects
  - object literals
    - var cat = { name: "Mici" }
  - constructor functions
    - function Cat() { this... }
    - this: refers to an object
  - Object.create
    - what's happening in the background
  - ES6 classes
    - class keyword: just syntactic sugar

### JS Object Properties

- reach property
  - bracket notation: cat['color'] (create properties from data entered by the user)
  - dot notation: cat.color
  - Object.getOwnPropertyDescriptor(cat, 'color')
- Object.freeze: make it immutable
- Object.defineProperty
- for...in loop
- configurable property
- getter & setter

### Prototypes & Inheritance

- Object.defineProperty(Array.protoype)
- prototype: object instance
- Function's prototype
  - will become the prototype for all objects created with this ctor function
  - Cat.prototype
- object's prototype
  - from which the object is inherited
  - cat.__proto__
- instance vs prototype properties
- Object.prototype = null
- class = syntactic sugar over prototypes

## Practical Design Patterns in JS

### What is a design pattern

- JS originally: to manipulate the DOM
- now
  - node.js: backend
  - elektron: desktop
- Design Pattern: Elements of Reusable Object-Oriented Software (Gamma, Helm, Johnson, Vlissides)
- **design pattern** what
  - an arrangement to solve a problem
  - solves a problem
  - proven concept
  - solution is not obvious
  - deals with a relationship, interaction
- **design pattern** why
  - why do it again
  - common vocab
- **design pattern** types
  - creational
    - ctor
    - module
    - factory
    - singleton
  - structural
    - decorator
    - facade
    - flyweight
  - behavioral
    - command
    - mediator
    - observer

### Objects in JavaScript

- object creation
  - curly braces
  - Object.create
  - new Object() - not recommended
- read & write attributes
  - dot notation
  - square bracket - you can use paramteres
- defining properties
  - Object.defineProperty
    - value
    - writable: cannot be overwritten
    - configurable: cannot be redefined
    - enumerable: hide from keys
- inheritance
  - Object.create

### Creational design patterns

#### Constructor Pattern

- new keyword
  - new object
  - link object to a prototype
  - bind 'this'
- node: require
- classes: EcsmaScript2015
  - only in strict mode
  - constructor
  - functions without keywords

#### Module pattern

- objective
  - ~toolbox
  - collection of keys & functions
  - private variables
- Ctor: we have a bunch of them
- Module: we only have one instance
- reveal module pattern
  - ~documentation

#### Factory pattern

- objective
  - simplifies object creation
  - creating different objects based on need
- simple if-else
- cache
- bgulp-load-plugin

#### Singletion

- objective
  - only one instance
  - on the first will be created
- CommonJS
- module.exports = new repo/repo() // node.js
- Angular: all services are singletons
  - app.service

### Structural Design Pattern

- how objects are made up & realtionships between them
- extend/simplify funtionality

#### Decorator Pattern

- objective
  - more complex inheritance
  - wrapping
  - protect existing object
- ~ override functions
- subobjecting with ~super ctor
- Task.prototype.save.call(thsi)
- Angular
  - decorate services: app.decorator, using $delegate

#### Facade Pattern

- objective
  - simplifies the interface
  - hides the chaos
  - wrapper
  - JQuery
- not adding (decorator), just hiding

#### Flyweight Pattern

- objective
  - smaller memory footprint
  - share data across objects
  - only useful for large number of objects

### Behavioral Design Pattern

- interaction between objects
- cooperation
- hierarchy

#### Observer Pattern

- objective
  - to watch other objects
  - notify
- one in focus, many watching
- vocab
  - observers
  - subject: list of observers & notify
- make subject with decorator

#### Mediator Pattern

- objective
  - loosely coupled system
  - one manager
  - many to many relationship

#### Command Pattern

- objective
  - decouple execution from implementation
  - allows undo
  - supports auditing & logging

## Advanced Technologies in JavaScript and jQuery

### Introduction

- functiion myFunc(){}                  // most common
- myFunc = function(){}                 // clearer
- var myFunc = function(){}             // scope is the current containing block
- var myObj = { myFunc: function(){} }  // include object in an object
- myObj = { myFunc: function(){} }      // single global object, ~namespace

- dealikng with legacy code
  - Stub
    - rename old function, make a stub for the old one
    - (+) no duplicate code
    - (-) multiple versions are not supported, stub is called, not the new version
  - Default Values
    - (+) for optional params
    - (-) no native js support
  - Object Parameter
    - single object parameter
    - extend object
    - no specific order
    - no placeholder for undefined
- js does not enforce the existence of params
- js ignores extra params

### Event Handling

- select element by #id or .class
- jQuery: $
- func.call(): first element is the *context* not the param we're expecting
- chaining event handler attachments
- event handler return value: not supposed to be present
- event handlers
  - .bind() - .unbind(): attaches copies, only to elements currently in the list
  - .live() - .die(): adds also new objects, no copies, efficiency issues
  - .delegate() - .undelegate(): robust version of live
  - .on(): bind, live, delegate
  - .off(): unbind, unlive, undelegate
  - .one(): process only one time

### Advanced Event Handling

- shorthand method: .click(), .bclick()...
- event handle methods: .on('click dbclick')

- attach happends on each refresh
- .off(): remove all event handlers
- named function
- event namespace
  - to only remove handlers we added
  - click.namespace, mousedown.namespace

- custom event
  - ßthis = $(this): $this.data
  - $this.trigger()
  - event.stopPropagation
  - apply custom event on objects not part of the DOM
    - $(internalObject).trigger: $(ob): create a jQuery object
    - attach event listener
      - $(internalObject).on('customEvent')
  - as equal as system events

- event params
  - $({nodeName : 'NAME'})
  - .on('eventName', function(event, param){})
  - .on('eventName', param, function(event){})
    - event.data
    - params are passed as pointers
