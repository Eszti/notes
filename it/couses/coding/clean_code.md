# Clean Code

Reading : Writing = 10:1

## Naming

- intention revealing
  - no comments
  - what is measured and what the unit is: reveal intent
  - write classes
- no disinformation
  - avoid platform variants
  - no "list" for not lists
- distinction
  - no numbering
  - noise words: ProductInfo,ProductData
  - never "variable"
- pronounceable names
  - social activity, easier to explain to new developers
- searchable names
  - The length of a name should correspond to the size of its scope
  - single-letter names only as local variables
  - rather longer names
- no encoding
  - Hungarian Notation: Simonyi Károly, e.g.: arru8NumberList, only in untyped languages
  - Java: strongly typed, don't use
  - no "m_" prefix for members
  - rather encode IF
  - no mental maps (r = url...)
- class names
  - noun/noun phase
  - avoid: Manager, Processor, Info, Data...
- method names
  - verb/verb phrase
  - accessors: get, set, is
  - constructor overloading < builder
- no cuteness, no jokes
- one word per concept
  - get, fetch, retrieve / controller, manager
- don't pun
  - paperback model over academic model
- use solution domain names: visitor, queue
- use problem domain names: domain experts can be asked
- meaningful comtext
  - use classes
  - break into smaller functions, variables can have a better context
- no gratuitous context: e.g. GSD prefix
  - short names > long names

## Functions

- small: 20-- lines
- if, else, while... should be one line long
- should not hold nested structures
- indent level: 1-2
- do one thing
  - doing steps that are one abstraction level below
  - read top-bottom, reformat with TO
- switch: too long, violates SRP and OCP
- descriptive names, it's okey to be long
- function arguments
  - indeal number 0, more than 3 should be avoided: story telling, testability;
    - monads:ok
    - dyads: if ordered, assert(exp, act): encode it into the function name
  - output arguments: no-go, change the state of the owning object
  - event: 1 argument, void
  - no flag args (bool): more than 1 thing
  - function/argument -> verb-noun form
- do sg or answer sg
- exceptions > return code, extract try/catch bodies
- Dont repeat yourself: since subroutines, like database normal forms
- Structured programming: Dijkstra
  - one return, no break, continue; never-ever goto

## Comments

- evil: express yourself in code
- best practice: create a function that says the same thing as the comment
- good comments:
  - legal
  - informative: most probably can be avoided by moving the code to a class/function or by renaming
  - explain intent: probably not agree but at least understandable
  - clarification
  - consequences, but better use @ignore
  - Todo: with ide
  - javadoc: public API, but strictly only public!!
- bad comments:
  - almost all
  - mumbling
  - redundant
  - not every function MUST have a javadoc
  - journal (change log) --> source control
  - noise (the day of the month), copy-paste errors
  - position markers
  - edited by, commented out code!
  - no html in comment (tool should do this)
  - nonlocal
  - too much information

## Formatting

- important!!
- Fitness typical file size: 200 lines, upper limit of 500
- vertical formatting:
  - newspaper metaphor: topmost part: high-level
  - thoughts separated with blank lines
  - variables at the top of each function
  - dependent functions: close, caller above the callee
  - concenptual affinity: e.g. similar signature
- horizontal formatting:
  - suggested: 120
  - do indent
  - space for assignment, math precedence
  - avoid collapsing scopes
  - avoid dummy if/while...
- team rules over individual preferences
- Uncle Bob: so small functions, that no blank lines at all are needed

## Objects and Data Structures

- abstraction
  - do not expose data internal structure
  - different setter & getter
- law of Demeter: don't talk to strangers, call: paramter, fields, created and instance methods
  - data sructors: only public (or bean)
  - object: hidden inner structure
