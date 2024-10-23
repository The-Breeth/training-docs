---
title: FrontEnd
type: docs
weight: 2
prev: docs/Front End/1leaf
next: docs/Front End/3leaf
---

# React Hooks and State Management with Redux

## Overview

In this section, we'll dive into React Hooks, a key feature of React that allows you to manage component state and side effects. Additionally, we’ll cover Redux, a state management library often used in React applications to handle global application state in a predictable manner.

### React Hooks

- **Description**: React hooks are functions that let you "hook" into React features, such as state and lifecycle methods, without writing class components. They provide a simpler and more functional approach to building React applications.
- **Benefits**:
  - React hooks for state management and other useful scenarios.

### Commonly Used React Hooks

### useState

- **Description**: Allows you to add state to functional components. It returns a stateful value and a function to update it.
- **Usage Example:**:

```
import React, { useState } from 'react';

function Counter() {
 const [count, setCount] = useState(0);

 return (
   <div>
     <p>You clicked {count} times</p>
     <button onClick={() => setCount(count + 1)}>Click me</button>
   </div>
 );
}
```

### useEffect

- **Description**: Lets you perform side effects in functional components, such as fetching data, directly manipulating the DOM, or subscribing to events.

- **Usage Example:**:

```
import React, { useState, useEffect } from 'react';

function Timer() {
 const [seconds, setSeconds] = useState(0);

 useEffect(() => {
   const interval = setInterval(() => {
     setSeconds(seconds => seconds + 1);
   }, 1000);
   return () => clearInterval(interval);
 }, []);

 return <div>Seconds: {seconds}</div>;
}

```

### useContext

- **Description**: Allows you to access context values without explicitly passing props down through multiple levels.
- **Usage Example:**:

  ```
  import React, { useContext } from 'react';
  const ThemeContext = React.createContext('light');
  function ThemedButton() {
  const theme = useContext(ThemeContext);
  return <button className={theme}>I am styled by theme context!</button>;
  }

  ```

### useReducer

- **Description**:A more advanced alternative to useState for managing complex state logic or when state transitions depend on previous state. It mimics the reducer pattern used in Redux.
- **Usage Example:**:

```
import React, { useReducer } from 'react';

const initialState = { count: 0 };

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return { count: state.count + 1 };
    case 'decrement':
      return { count: state.count - 1 };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <div>
      <p>Count: {state.count}</p>
      <button onClick={() => dispatch({ type: 'increment' })}>+</button>
      <button onClick={() => dispatch({ type: 'decrement' })}>-</button>
    </div>
  );
}

```

### useRef

- **Description**: Allows you to persist values across renders or directly access a DOM element.

- **Usage Example:**:

```
import React, { useRef, useEffect } from 'react';

function TextInputWithFocusButton() {
  const inputEl = useRef(null);
  const onButtonClick = () => {
    inputEl.current.focus();
  };
  return (
    <div>
      <input ref={inputEl} type="text" />
      <button onClick={onButtonClick}>Focus the input</button>
    </div>
  );
}
```

### useMemo

- **Description**:Optimizes performance by memoizing expensive computations, preventing unnecessary recalculations on every render.
- **Usage Example:**:

```
import React, { useState, useMemo } from 'react';

function ExpensiveComponent({ number }) {
  const compute = useMemo(() => {
    return heavyComputation(number);
  }, [number]);

  return <div>{compute}</div>;
}

```

### useCallback

- **Description**: Returns a memoized version of a callback function that only changes if its dependencies change, preventing unnecessary re-renders.

- **Usage Example:**:

```
import React, { useCallback } from 'react';

function Parent() {
  const memoizedCallback = useCallback(() => {
    doSomething();
  }, []);

  return <Child callback={memoizedCallback} />;
}

```

### Introduction to Redux

- **Description**:Redux is a predictable state container for JavaScript applications, commonly used with React. It helps manage the global state of your application, making state transitions predictable and maintainable by following a strict unidirectional data flow..
- **Key Concepts in Redux**:
- Store: The central place where the application's state is kept. It holds the complete state tree of the application.

- Action: A plain JavaScript object that describes what changes should happen in the state. Actions typically have a type property to indicate the type of action being performed.

- Reducer: A pure function that determines how the state changes in response to an action. It takes the previous state and the action as inputs and returns the new state.

- Dispatch: A method used to send an action to the store, triggering a state update.

- Middleware: Functions that intercept actions before they reach the reducer, allowing you to perform side effects like asynchronous API calls.

- **Redux Workflow**:
- Dispatching an action: The user interacts with the app, which triggers an action.
- Reducer updates the state: The reducer processes the action and returns the updated state.
- Store updates the UI: The new state is stored, and the UI re-renders to reflect the changes.

## Conclusion

React Hooks simplify component logic and state management, making your application more modular and easier to maintain. Redux complements React by providing a predictable and centralized way to manage global state. Together, they form a powerful combination for building scalable React applications.

```

```