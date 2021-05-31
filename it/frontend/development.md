# Development

## A11y

### Accessibility

- to design products for people with disabilities
  - permanent (physical or mental)
  - temporary (broken arm...)
  - situational (bright sunlight...)
- ensure
  - direct / unassisted access
  - indirect / compatibility with a person's assistive technology (e.g. computer screen readers)

### Tools

- [eslint-plugin-jsx-a11y](https://github.com/jsx-eslint/eslint-plugin-jsx-a11y#readme)
  - static AST checker for a11y in react
- [jest-axe](https://github.com/nickcolley/jest-axe)
  - a11y testing with jest

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

### UI Elements

- modal window: a subordinate to an application's main window