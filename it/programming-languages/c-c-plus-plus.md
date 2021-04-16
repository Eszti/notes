# C / C++

## C++

### C++20

- modules
  - no more #inluce
  - export & import
  - faster compiliation, no more .h/.cpp
- concepts
  - requires(): compiler feature with static_assert, constraints for templates
  - conceipts: complie time predicate, template definition (e.g. what behaves like a boolean)
- ranges
  - a conceopt
  - e.g. sort without .begin() & .end()
  - views: requirements of a range with O(1) copy/move/assignment operations
  - pipes: applicable for unary adopters
- coroutines
  - co_yield, co_return, co_await
  - 2 types: with & w/o stack
  - e.g. for generators, lazy evaluation, event driven programming
- lambdas (since C++11)
  - default initialisation, can be members