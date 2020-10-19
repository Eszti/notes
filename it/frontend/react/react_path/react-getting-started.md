# Getting started

## The Basics

- 16.8 Hooks

- Why React
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

- React's Basic Concepts
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

- First Hook
  - immutable props but mutable state
  - useState
  - curly braces: code
  - onClick: function reference: {...}

- First one-way data flow
  - ReactDOM.render
    - each element gets translated into a function call
    - render an array of element
    - enclose multiple elements into a (div) parent: React.Fragment can be used == <>
    - each component has props
      - can hold functions
  - standard React event: onClick, onSubmit

- tree reconciliation
  - React.createElement(tag, arguments, content)
  - smart diffing
  - virtual DOM
    - last UI is in memory
    - compare new with the last
    - instruct browser: only partial update
  - not imerative, but declarative

## Modern JS Crash Course

- block scopes
  - var is availably outside
  - let: only in block
- function scope
- const
  - reference does not change
  - use for all variables

- arrow functions vs function()
