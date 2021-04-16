# React 

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

## Getting started

- `npm init react-app my-app`
- files
	- App.js
		- React App Component
	- App.test.js
		- unit tests
	- App.css
		- style

## Components

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

## States

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

## Rendering

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

## React Context

- for global information
- e.g. language/i18n

## Styling

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

## Testing

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

## Redux

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
