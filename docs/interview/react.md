# React Interview Questions

React is a fast and free open source javascript library used for building user interfaces and ui components. React was originally created by facebook and is currently being maintained by facebook and the community.

## Table of Content

- [Explain the difference between the Virtual DOM and Real DOM.](#explain-the-difference-between-the-virtual-dom-and-real-dom)
- [What is JSX?](#what-is-jsx)
- [What are life cycle hooks?](#what-are-life-cycle-hooks)
- [What are the differences between a class component and functional component?](#what-are-the-differences-between-a-class-component-and-functional-component)
- [What is the difference between state and props?](#what-is-the-difference-between-state-and-props)
- [What are controlled components?](#what-are-controlled-components)
- [What is a higher order component?](#what-is-a-higher-order-component)
- [What is Redux?](#what-is-redux)

### Explain the difference between the Virtual DOM and Real DOM.

Virtual DOM is basically a copy of the Real DOM. Whenever a change occurs in the virtual DOM it will re-render that certain part of the DOM. That is why it may appear faster compared other frameworks where the entire DOM is re-rendered.

### What is JSX?

JSX stands for Javascript XML. It allows us to write HTML inside JavaScript and place them in the DOM without using functions like `appendChild()` or `createElement()`.

### What are Life Cycle Methods?

Life cycle methods are generally referred to the methods inside a class component life cycle phases. The phases are mounting, updating, umounting and in each phase there are methods you may tap into and to trigger changes. Some of these methods may be immitated with hooks in a functional components.

### What are the differences between a class component and functional component?

Before the introduction of hooks in React, functional components were considered stateless components. Now people generally prefer using functional components over class components since hooks immitates most if not all of the features of a class components and hooks may be reused while class methods may not. In terms of performance they are about the same but functional components are considered cleaner but that is subjective.

### What is the difference between state and props?

State is an object where you store property values that belongs to the component. Props are state or prop passed down from other components. A big difference between states and props are that states are mutable while props are ready-only and immutable. Any changes in the property values of a state will result in a re-render.

### What are controlled components?

Controlled and uncontrolled components are just different approaches to handling input form elements in react. In a controlled component the value of the input element is controlled by React. In an uncontrolled component, the value of the input element is handled by the DOM itself. It is recommened to use controlled component over uncontrolled

### What is a higher order component?

### What is Redux?

### What are Hooks?

Hooks are functions that let us create stateful functional components. Prior to the release of hooks, functional components or stateless component were just used to render dummy component.

### What are the different ways to style a React component?

There are many ways you can style a react component. You can directly style an element with the style attribute using inline styling or javascript object. Another way you can style a component is by creating a separate css file and import it into your component with the className attribute. There are also external libraries you may use to style component such as styled-components or reactstrap which follow their own conventions.
