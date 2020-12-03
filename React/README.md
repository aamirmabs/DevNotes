# React DevRef <!-- omit in toc -->

- [Creating Elements and JSX](#creating-elements-and-jsx)
  - [JSX Rules and Limitations](#jsx-rules-and-limitations)
- [Components](#components)
  - [Class Components](#class-components)
  - [Functional Components](#functional-components)
  - [Usage](#usage)
- [Props](#props)
  - [Props in Class Components](#props-in-class-components)
  - [Props in Functional Components](#props-in-functional-components)
  - [props.children](#propschildren)
- [State](#state)
- [Events in React](#events-in-react)

## Creating Elements and JSX

```javascript
React.createElement( /* type */, /* props */, /* content */ );
```

### JSX Rules and Limitations

1. Cannot use reserved words. Must use an alternative word. For Example, we cannot use the keyword 'class' but should instead use 'className' to specify a class for an element.
2. JSX can return only one element. All elements must be nested withing that element.

   - Invalid JSX

     - ```JSX
       <div className="App">
         <h1>React App Here</h1>
       </div>
       <h2>Another heading</h2>
       ```

   - Valid JSX

     - ```JSX
       <div className="App">
         <h1>React App Here</h1>
         <h2>Another heading</h2>
       </div>
       ```

3. Next point

## Components

### Class Components

- Also referred to as "containers", "smart" or "stateful" components

```javascript
class Cmp extends Component {
  render() {
    return <div>some JSX</div>;
  }
}
```

```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### Functional Components

- Also referred to as "presentational", "dumb" or "stateless" components

```javascript
const cmp = () => {
  return <div>some JSX</div>;
};
```

```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```

```javascript
import React from "react";

const Person = () => {
  return (
    <div>
      <h4>This is Person Component</h4>
    </div>
  );
};

export default Person;
```

- Can execute one-line expressions. Cannot execute complex functions.

```javascript
const Person = () => {
  return (
    <div>
      <h4>This is Person Component</h4>
      <p>Age: {Math.floor(Math.random() * 30)}</p>
    </div>
  );
};
```

### Usage

Text here

## Props

React Props are like function arguments in JavaScript and attributes in HTML.

`props` allow you to pass data from a parent (wrapping) component to a child (embedded) component.

### Props in Class Components

To send props into a component, use the same syntax as HTML attributes:

```javascript
const myelement = <Car brand="Ford" />;
```

We can use the prop passed in the class component as follows:

```javascript
class Car extends React.Component {
  render() {
    return <h2>I am a {this.props.brand}!</h1>;
  }
}
```

### Props in Functional Components

Similar to how props are used in class components can be used in functional components but they are not needed to be referenced to the `this` object. That is, in functional components the pops can be accessed with `props.object` instead of the `this.props.object` in class components.

```javascript
const myelement = <Car brand="Ford" />;
```

We can use the prop passed in the functional component as follows:

```javascript
const Car = (props) =>{
  return (
    <h2>I am a {props.brand}!</h1>;
  )
}
```

### props.children

Content that is passes between the opening and closing tags of a component can be accessed with `props.children`.

```javascript
const myelement = <Car brand="Ford">I am red in color</Car>;
```

We can use the prop passed in the functional component as follows:

```javascript
const Car = (props) =>{
  return (
    <h2>I am a {props.brand}!</h1>;
    <p>{props.children}</p>
  )
}
```

## State

`state` simply is a property of the component class. You can access it via `this.state` in your class JSX code (which you return in the required `render()` method).

Whenever `state` changes, the component will re-render and reflect the new `state`. The difference to props is, that this happens within one and the same component - you don't receive new data (`props`) from outside!

React components has a built-in state object. The state object is where you store property values that belongs to the component.

When the state object changes, the component re-renders.

State is stored on the parent component and modified on calling.

Whilst `props` allow you to pass data down the component tree (and hence trigger an UI update), `state` is used to change the component `state` from within. Changes to `state` also trigger an UI update.

Only class-based components can define and use `state` . You can of course pass the `state` down to functional components, but these then can't directly edit it.

```javascript
class NewPost extends Component {
  // state can only be accessed in class-based components!
  state = {
    counter: 1
  };

  render() {
    // Needs to be implemented in class-based components! Needs to return some JSX!
    return <div>{this.state.counter}</div>;
  }
}
```

## Events in React

```javascript
class App extends Component {
  eventHandler = () => {
    console.log("Event here");
  };

  render() {
    return (
      <div className="App">
        <h1>React App Here</h1>
        <button onClick={eventHandler}>Switch Name</button>
        // attach the event function(eventHandler) to the element action
        (onClick)
      </div>
    );
  }
}
```
