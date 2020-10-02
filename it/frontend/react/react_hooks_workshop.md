# React Hooks

## Intro

- React UI framework, based on components
  - class (past, only class)
  - functiional

- class lifecycle
  - mounting: componentDidMount
    - add event listener
    - initial data loading
  - updating: componentDidUpdate
    - data update
  - unmounting: componentWillUnmount
    - remove event listener

- issues with lifecycle
  - hard to reuse logic (distributed among different lifecycle phases)
  - complex components are hard to understand

## Basic Hooks

- hooks
  - allow states without a class
  - backwards compatibility with classes
  - convention: name starts with "use"

  - useState
    - initialize with initial state
    - returns current state & setter
  - useEffect
    - group by semantic logic instead of lifecycle method
    - parameters, aka dependency array
      - without: always (mount, update, unmount)
      - params: developer can declare when to call (reference compare), only invoked if params change
      - []: didMount, willUnmount, but not on update
  - useCustom
    - combibation of useState & useEffect
  - linting
    - hooks are either inside
      - PascalCase function (supposed to be a function component)
      - useSomething (supposed to be a custom Hook)
    - hooks are always called in the same order

## Testing

- hook ~ js function
- problem
  - hooks can only be called inside of a FC
- solution
  - test the component that uses the hook
  - actual component
    - hook is designed specially for this component
    - component has a suitable interface
  - test component
    - interface can be designed freely
    - boilerplate code
- testing frameworks
  - [enzyme](https://enzymejs.github.io/enzyme/)
    - shallow
      - does not call mount
      - only initialisation can be tested
    - mount
      - calls mount
  - [react hooks testing library](https://react-hooks-testing-library.com/reference/api)
    - no boiler plate code for component
    - a bit difficult interface
- act: test actions

## Additional Hooks

- Redux
  - useSelector
  - useDispath
- GraphQL
  - useQuery
  - useMutation
- performance optimization
  - no guarantees, code must work also without cache
  - useCallback
    - ~syntactic sugar
  - useMemo
    - ~ cache
  - useRef
    - access child imperatively
    - variable can be edited withour rerendering
  - useContext

## Redux Hooks

- Redux store
  - connect + selector -> useSelector
  - connect + dispatch -> useDispatch
- connect: unit testing without Provider
- redux hooks: no boilder plate

## Conclusion

- classes still exist
- hooks allow splitting into smaller components
- lots of libraries provide hookse
