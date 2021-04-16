# TypeScript: The Big Picture

## How TypeScript Can Help

- superset of javascript
- for making javascript more convinient
- javascript
  - support from most browsers
  - was designed for simple functionalities
- typescript
  - interpreted
  - compiles to javascript (transcompile)
  - no runtime
- typescript features
  - static types
  - organization
    - classes (js also supports)
    - namespaces
    - modules
    - interfaces
  - tooling support
    - autocomplete, syntax check
    - analysis, e.g. unused...
    - IDE support

## Setting Up a TypeScript Development Environment

- real benefit is for complex/larger applicationns
- extension: ts
- compiler: tsc
  - generates js
    - do not even look into it
  - can be watched
- to start
  - IDE
  - tsc
  - npm
    - install other development tools
    - typescript can be installed
- project
  - no defined folder structor
  - tsconfig.json
    - configuration
    - tsc --init: to generate

## Writing TypeScript Applications

- types
  - type inferencing
  - default: any
  - variables, params, return values
- class is like java, C#...
  - support inheritance: extends
  - access modifier
    - default: public
  - supports: readonly, getter, setter...
- modules
  - module loaders: e.g. CommonJS
  - you have to explicitely export for availability
  - import for usage
- frameworks
  - angular, react, vue, node.js
- [learn here](https://www.typescriptlang.org/)
