# Virtual Dom

- Cannot directly update HTML
- Acts as a copy of the real DOM, which can be frequently manipulated and updated without a page refresh
- More of a pattern than a specific technology
- Synced with the real dom with 'react-dom'
- Diffing, detects changes compared to the actual dom and changes only that portion of the dom

## Real Dom

- Directly updates and manipulates HTML
- Creates a new DOM/Full repaint if it is updated
- An object-based representation of HTML document + an interface for manipulating that object

## Shadow Dom

- Browser Specific Technology

## Limitations

- Library not a framework
  - Pros and Cons for the freedom it gives you since its a library
  - Fairly Large
  - Manage by a big company even though it is open source, facebook

## JSX

- Short for Javascript XML
- Write javascript with an HTML-like template syntax, it is not html
- Produces elements that represent objects

## Element vs Component

- Element is something that is created by JSX as an object
- Component is a function that returns an element

```jsx
import React from 'react'
import ReactDOM from 'react-dom

const component = () => React.createElement('div', null, 'element');
// ReactDOM.render(<component />, document.getElementById('root'));
const Component = () => <div>element</div>;
// ReactDOM.render(<Component />, document.getElementById('root'));
const Element = <div>element</div>;
// ReactDOM.render(Element, document.getElementById('root'));
```

## Props

- Passing value from parent to child
- To pass a value from child to parent, you must use a function passed down from parent to child as a prop
- **Prop drilling**, passing probs down multiple levels
- You cannot modify props, its readonly

## State and Lifecycle in class components

- State is scoped and local to a given component
- State in a class component is attached to a class object so its persistent, state in a functional component is recalled multiple time
- Mount
  - render, componentDidmount are called when components are mounted or put on a page, initalization
- Updating
  - render, componentDidUpdate are run whenever the component updates
- Unmounting
  - componentWillUnmount are called whenever the component is removed from the page

## UseEffect

```jsx
useEffect(() => {
  //your code goes here
  return () => {
    //your cleanup code codes here
  };
}, []);
```

- []
  - Runs on mount
- [variable]
  - Runs on mount and when variable changes
- No Array
  - Runs on mount and on every state changes
- useEffects function return value is an cleanup function that cleanup event listener, etc
  - basically an unmount function

## Refs

- Best time to use refs
  - Managing focus or media
  - Triggering animations
  - Integrating with DOM libraries

## Context

- Only use when necessary, do not over use

## Fragment

- Basically a container to wrap content instead of using divs

## Higher Order Component

- Function takes in a component and returns a new component

## Portal

- Way to render children into a dom node that exist outside of hierarchy of the parent component, or anywhere on the dom tree
- Mainly see it in Modals

## Controlled and Uncontrolled Component

- Uncontrolled
- Controlled components uses react to keeps track of its state and changes
