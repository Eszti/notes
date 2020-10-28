# TypeScript: Getting Started

## Install & configure typescript

- install ts
  - `npm install -g typescript`
  - package.json
    - store info about the npm packages
    - devDependencies
      - only used for development

- compile ts
  - `tsc app.ts`
  - with tsconfig just `tsc`

- start webserver
  - use webpack

- configure ts project files
  - tsconfig.json
    - compiler options
    - files to be in- & excluded
    - supports config inheritance
  - to create config file
    - `tsc --init`
  - most common options
    - target: which js version
    - sourceMap: for debugging
    - outDir: where to put the js files
    - strict: strict type-checking
    - whatch: leaves the compliler running
    - files: which files we want to complie
    - include: pattern for files, e.g. `./**/*.ts` (all subdirs as well)
  - inherit configs
    - extends

  - webpack
    - to bundle client code
    - options
      - entry point
      - module: where to find plugins
      - output: budle name, will be sent to the browser (stored only in memory)
      - devServer: inline: if false browser won't refresh when new bundles are produced

## Taking advance of built-in type

- Boolen, Number, String, Array, Enum (not available in js)
- hoisting: js, moving all declarations to the top
- type annotations
  - let x: string, only type I can ever assign
  - let x = "", also remains a string
- Void, Null, Undefined, Never (return value for functions that never return), Any
- union types: number | string
- strict null checks: string | null
- type assertions
  - "you know better"
  - `<number>value`
  - `value as number`
- control flow type analysis
  - always checks against the most specific type
