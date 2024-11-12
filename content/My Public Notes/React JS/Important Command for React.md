## Important commands used in terminal in react

Success! Created demo at C:\Users\chels\OneDrive\Documents\react\demo
Inside that directory, you can run several commands:

  npm start
    Starts the development server.

  npm run build
    Bundles the app into static files for production.

  npm test
    Starts the test runner.

  npm run eject
    Removes this tool and copies build dependencies, configuration files
    and scripts into the app directory. If you do this, you can’t go back!

We suggest that you begin by typing:

  cd demo
  `npm start`

Happy hacking!

note: cd is to move you to another folder and to make sure you are in the right folder

## if using vite
to run the app just simply type `npm run dev`

## React basic
Of course! React is a powerful JavaScript library for building user interfaces, particularly single-page applications where you need to render components dynamically. Here are the key concepts you need to understand as a beginner:

### 1. Components

- **Definition**: Components are the building blocks of a React application. They are reusable pieces of UI.
- **Types**: There are two main types of components:
  - **Functional Components**: Simple functions that return JSX (JavaScript XML) and can use hooks.
  - **Class Components**: ES6 classes that extend `React.Component` and have lifecycle methods.

**Example**:
```jsx
// Functional Component
function HelloWorld() {
  return <h1>Hello, World!</h1>;
}

// Class Component
class HelloWorld extends React.Component {
  render() {
    return <h1>Hello, World!</h1>;
  }
}
```

### 2. JSX (JavaScript XML)

- **Definition**: JSX is a syntax extension for JavaScript that looks similar to HTML. It's used to describe what the UI should look like.
- **Why JSX**: It allows you to write HTML directly within JavaScript, making it easier to create and visualize UI components.

**Example**:
```jsx
const element = <h1>Hello, World!</h1>;
```

### 3. State and Props

- **State**: A component's state is an object that holds some information that may change over the lifetime of the component.
  - **useState Hook**: In functional components, you use the `useState` hook to manage state.
  
**Example**:
```jsx
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

- **Props**: Short for "properties," props are read-only inputs that allow data to be passed from one component to another.
  
**Example**:
```jsx
function Greeting(props) {
  return <h1>Hello, {props.name}</h1>;
}

function App() {
  return <Greeting name="Alice" />;
}
```

### 4. Handling Events

- **Definition**: Handling events in React is similar to handling events in DOM elements. However, you use camelCase syntax for event handlers and pass functions as event handlers.
  
**Example**:
```jsx
function Button() {
  const handleClick = () => {
    alert('Button was clicked!');
  };

  return <button onClick={handleClick}>Click me</button>;
}
```

### 5. Lifecycle Methods (Class Components) / Hooks (Functional Components)

- **Lifecycle Methods**: Methods that get called at different stages of a component’s life in class components (e.g., `componentDidMount`, `componentDidUpdate`, `componentWillUnmount`).

**Example**:
```jsx
class MyComponent extends React.Component {
  componentDidMount() {
    // Code to run when the component mounts
  }

  componentDidUpdate() {
    // Code to run when the component updates
  }

  componentWillUnmount() {
    // Code to run when the component unmounts
  }

  render() {
    return <div>My Component</div>;
  }
}
```

- **Hooks**: Special functions in functional components that let you use state and other React features (e.g., `useEffect` for side effects).

**Example**:
```jsx
import React, { useEffect, useState } from 'react';

function MyComponent() {
  const [count, setCount] = useState(0);

  useEffect(() => {
    // Code to run when the component mounts and updates
    console.log('Component has mounted or updated');

    return () => {
      // Code to run when the component unmounts
      console.log('Component will unmount');
    };
  }, [count]); // Only re-run the effect if count changes

  return (
    <div>
      <p>Count: {count}</p>
      <button onClick={() => setCount(count + 1)}>Increment</button>
    </div>
  );
}
```

### 6. Conditional Rendering

- **Definition**: Rendering different UI elements based on certain conditions.
  
**Example**:
```jsx
function Greeting(props) {
  const isLoggedIn = props.isLoggedIn;

  if (isLoggedIn) {
    return <h1>Welcome back!</h1>;
  } else {
    return <h1>Please sign up.</h1>;
  }
}

function App() {
  return <Greeting isLoggedIn={true} />;
}
```

### 7. Lists and Keys

- **Definition**: Rendering lists of data in React using the `map` method, and using keys to help React identify which items have changed.
  
**Example**:
```jsx
function ListItems(props) {
  const items = props.items;
  return (
    <ul>
      {items.map((item, index) => (
        <li key={index}>{item}</li>
      ))}
    </ul>
  );
}

function App() {
  const items = ['Apple', 'Banana', 'Cherry'];
  return <ListItems items={items} />;
}
```

### 8. Forms and Controlled Components

- **Definition**: Managing form inputs with state in React. Controlled components have their form data controlled by React.
  
**Example**:
```jsx
import React, { useState } from 'react';

function MyForm() {
  const [value, setValue] = useState('');

  const handleChange = (event) => {
    setValue(event.target.value);
  };

  const handleSubmit = (event) => {
    alert('A name was submitted: ' + value);
    event.preventDefault();
  };

  return (
    <form onSubmit={handleSubmit}>
      <label>
        Name:
        <input type="text" value={value} onChange={handleChange} />
      </label>
      <button type="submit">Submit</button>
    </form>
  );
}
```


[[React Notes]]
#reactjs




