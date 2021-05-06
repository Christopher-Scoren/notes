# Content
1. Introduction
2. Advanced Components


## Introduction

React applications are made out of components.
Create and render a react component:
```
import React from 'react';
import ReactDOM from 'react-dom';
 
class MyComponentClass extends React.Component {
  render() {
    return <h1>Hello world</h1>;
  }
};
 
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```
the DOM is used in React applications, but it isn’t part of React. Methods imported from 'react' are only for pure React purposes, such as creating components or writing JSX elements.

* We can use a JavaScript class to define a new React component. We can also define components with JavaScript functions.  
* Component class variable names must begin with capital letters!  
* There is only one property that you have to include in your instructions: a render method.  
  * A render method is a property whose name is render, and whose value is a function.  
  * A render method must contain a return statement. Usually, this return statement returns a JSX expression (look at the code above)  
* To make a React component, you write a JSX element. Instead of naming your JSX element something like h1 or div like you’ve done before, give it the same name as a component class. Voilà, there’s your component instance! `<MyComponentClass />`

>JSX elements can be either HTML-like, or component instances. JSX uses capitalization to distinguish between the two! That is the React-specific reason why component class names must begin with capital letters. In a JSX element, that capitalized first letter says, “I will be a component instance and not an HTML tag.”

Whenever you make a component, that component inherits all of the methods of its component class. MyComponentClass has one method: MyComponentClass.render(). Therefore, <MyComponentClass /> also has a method named render. You could make a million different <MyComponentClass /> instances, and each one would inherit this same exact render method.

To call a component’s render method, you pass that component to ReactDOM.render(). Notice your component, being passed as ReactDOM.render()‘s first argument:
```
ReactDOM.render(
  <MyComponentClass />,
  document.getElementById('app')
);
```
* ReactDOM.render() will tell <MyComponentClass /> to call its render method.

## Advanced components

* However, a multi-line JSX expression should always be wrapped in parentheses
```
import React from 'react';
import ReactDOM from 'react-dom';

class QuoteMaker extends React.Component {
  render() {
    return (
      <blockquote>
        <p>
          The world is full of objects, more or less interesting; I do not wish to add any more.
        </p>
        <cite>
          <a target="_blank"
            href="https://en.wikipedia.org/wiki/Douglas_Huebler">
            Douglas Huebler
          </a>
        </cite>
      </blockquote>
    );
  }
};

ReactDOM.render(
  <QuoteMaker />,
  document.getElementById('app')
);
```
### Variable Attribute in a Component
```
...
const redPanda = {
  src: 'https://upload.wikimedia.org/wikipedia/commons/b/b2/Endangered_Red_Panda.jpg',
  alt: 'Red Panda',
  width:  '200px'
};

class RedPanda extends React.Component {
  render() {
    return (
      <div>
        <h1>Cute Red Panda</h1>
        <img 
          src={redPanda.src}
          alt={redPanda.alt}
          width={redPanda.width} />
      </div>
    );
  }
}
...
```

### calculations in render
```
class Random extends React.Component {
  render() {
    // First, some logic that must happen
    // before rendering:
    const n = Math.floor(Math.random() * 10 + 1);
    // Next, a return statement
    // using that logic:
    return <h1>The number is {n}!</h1>;
  }
}
```
The line with the const n declaration should not be part of the class declaration itself, but should occur in a method like render() as it is above.

### a Conditional in a Render Function

```
class TodaysPlan extends React.Component {
  render() {
    let task;
    if (!apocalypse) {
      task = 'learn React.js'
    } else {
      task = 'run around'
    }

    return <h1>Today I am going to {task}!</h1>;
  }
}
```
###  this in a Component

```
class IceCreamGuy extends React.Component {
  get food() {
    return 'ice cream';
  }
 
  render() {
    return <h1>I like {this.food}.</h1>;
  }
}
```
this refers to an instance of IceCreamGuy. The less simple answer is that this refers to the object on which this‘s enclosing method  
You don’t need those parentheses because .food is a getter method.

### Event Listener in a Component
```
class MyClass extends React.Component {
  myFunc() {
    alert('Stop it.  Stop hovering.');
  }
 
  render() {
    return (
      <div onHover={this.myFunc}>
      </div>
    );
  }
}
```
















